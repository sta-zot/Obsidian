# Полная шпаргалка по systemd: Units, Timers, Slices, Sockets и Targets

## 1. Основы Units (Юнитов) и структура файлов
Файлы конфигураций хранятся в двух основных директориях:
- **`/lib/systemd/system/`** — системные юниты, установленные из пакетов (не редактировать вручную).
- **`/etc/systemd/system/`** — пользовательские/кастомные юниты и переопределения (высший приоритет).
### Базовая структура юнита `.service`

```TOML
[Unit]
Description=My Application Service
Documentation=https://docs.internal/app
# Порядок и жесткость загрузки:
After=network.target network-online.target   # Запуститься ПОСЛЕ поднятия сети
Wants=network-online.target                 # Мягкая зависимость (попытается запустить)
Requires=postgresql.service                # Жесткая зависимость (упадет, если упадет DB)

[Service]
Type=simple                                # simple | exec | forking | oneshot | notify | dbus
User=appuser
Group=appuser
WorkingDirectory=/opt/myapp
ExecStartPre=/opt/myapp/bin/check-env.sh
ExecStart=/opt/myapp/bin/myapp --config /etc/myapp/config.yaml
ExecReload=/bin/kill -HUP $MAINPID
Restart=on-failure                         # always | on-failure | on-abnormal | no
RestartSec=5s

[Install]
WantedBy=multi-user.target                 # Включается при загрузке в multi-user mode
```
## 2. Timers (Таймеры) — Замена Cron
Состоят из пары файлов: **`app.timer`** и **`app.service`** (где сервис обычно имеет `Type=oneshot`).
### Параметры `[Timer]`

| **Директива**             | **Пример**                | **Назначение**                                                           |
| ------------------------- | ------------------------- | ------------------------------------------------------------------------ |
| **`OnCalendar=`**         | `Mon..Fri *-*-* 03:00:00` | Абсолютные даты и время (формат systemd time).                           |
| **`OnBootSec=`**          | `15min`                   | Таймер с момента завершения загрузки системы.                            |
| **`OnUnitActiveSec=`**    | `1h`                      | Таймер с момента **последней активации** сервиса (для регулярных задач). |
| **`Persistent=`**         | `true`                    | Выполнить пропущенную задачу при включении, если ПК был выключен.        |
| **`RandomizedDelaySec=`** | `5m`                      | Разброс времени старта для предотвращения пиковой нагрузки.              |
| **`Unit=`**               | `backup.service`          | Указывается, если имя `.service` отличается от имени `.timer`.           |

```TOML
# /etc/systemd/system/daily-backup.timer
[Unit]
Description=Run Daily Database Backup

[Timer]
OnCalendar=*-*-* 02:00:00
RandomizedDelaySec=30m
Persistent=true

[Install]
WantedBy=timers.target
```
## 3. Slices (Слайсы) и управление ресурсами (cgroups v2)
Слайсы позволяют создавать иерархическое дерево распределения ресурсов (CPU, RAM, I/O) для групп процессов.
### Иерархия слайсов по умолчанию:
- **`-.slice`** — корневой слайс.    
- **`system.slice`** — все системные сервисы и демоны.
- **`user.slice`** — пользовательские сессии (`user-1000.slice`).
### Ограничение ресурсов в `.service` или `.slice`

```TOML
[Service] # или [Slice]
# CPU
CPUAccounting=true
CPUQuota=200%                              # Максимум 2 ядра CPU

# RAM
MemoryAccounting=true
MemoryHigh=2G                              # Мягкий лимит (включает агрессивный reclaim)
MemoryMax=4G                               # Жесткий лимит (OOM-killer при превышении)
MemorySwapMax=1G                           # Лимит использования Swap

# I/O (Диск)
IOWeight=100                               # Приоритет ввода-вывода (1-1000, по умолчанию 100)
```
## 4. Sockets (Сокеты) — Активация по запросу (Socket Activation)
Позволяет systemd слушать порт/сокет до старта приложения и передавать готовый дескриптор процессу, экономя ресурсы RAM и ускоряя загрузку.
### Типы сокетов и права
- **`ListenStream=`** — TCP / UNIX domain stream socket (`SOCK_STREAM`).
- **`ListenDatagram=`** — UDP / UNIX domain datagram socket (`SOCK_DGRAM`).
- **`ListenFIFO=`** — Именованный канал в файловой системе (Named Pipe).
### Права и параметры `[Socket]`

```TOML
# /etc/systemd/system/app.socket
[Unit]
Description=App Socket

[Socket]
ListenStream=/run/myapp/app.sock
SocketUser=www-data
SocketGroup=www-data
SocketMode=0660                            # Права на файл сокета в FS

# Сетевые опции
Backlog=2048
NoDelay=true
KeepAlive=true

# Режим активации
Accept=no                                  # no = один сервис обрабатывает всё;
                                           # yes = отдельный экземпляр под каждого клиента

[Install]
WantedBy=sockets.target
```

> **Важно:** Для **TCP-портов** разница пользователей между `.socket` и `.service` не имеет значения (`bind` делает `root` в `systemd`). Для **UNIX-сокетов** права `SocketUser`/`SocketGroup` должны совпадать или пересекаться с пользователем сервиса через общую группу.
## 5. Targets (Таргеты) — Точки группировки и цепочки загрузки
Таргеты заменяют устаревшие Runlevels и задают состояние системы с помощью параллельного графа зависимостей (DAG).
### Сопоставление с SysVinit Runlevels

| **SysVinit Runlevel** | **systemd Target**  | **Описание**                                    |
| --------------------- | ------------------- | ----------------------------------------------- |
| **0**                 | `poweroff.target`   | Выключение.                                     |
| **1 (S)**             | `rescue.target`     | Однопользовательский режим восстановления.      |
| **3**                 | `multi-user.target` | Многопользовательский консольный режим с сетью. |
| **5**                 | `graphical.target`  | Графический режим (GUI).                        |
| **6**                 | `reboot.target`     | Перезагрузка.                                   |
### Конфигурация кастомного таргета

```TOML
# /etc/systemd/system/analytics.target
[Unit]
Description=Analytics Cluster Stack
After=multi-user.target
Wants=multi-user.target
Wants=analytics-db.service analytics-worker.service
AllowIsolate=true                          # Разрешает переключение через systemctl isolate

[Install]
WantedBy=multi-user.target
```
## 6. Главные команды управления (Шпаргалка консоли)
### Управление сервисами и сокетами

```Bash
systemctl daemon-reload                    # Перечитать файлы юнитов после изменений
systemctl start|stop|restart <unit>        # Запустить / Остановить / Перезапустить
systemctl status <unit>                    # Проверить статус и последние логи
systemctl enable|disable --now <unit>      # Включить/выключить автозапуск (+ запустить)
systemctl is-active|is-enabled <unit>      # Быстрая проверка состояния в скриптах
```
### Диагностика и Анализ загрузки

```Bash
systemd-analyze                            # Показать общее время загрузки ядра и юзерспейса
systemd-analyze blame                      # Список юнитов, отсортированный по времени старта
systemd-analyze critical-chain             # Дерево юнитов, влияющих на критическую цепь
systemd-analyze verify /path/to/unit       # Проверить синтаксис файла юнита
```
### Управление таргетами


```Bash
systemctl get-default                      # Показать таргет по умолчанию
systemctl set-default multi-user.target    # Поменять таргет по умолчанию на консольный
systemctl isolate rescue.target            # Мгновенно переключить систему в таргет сброса
```
### Таймеры и Ресурсы

```Bash
systemctl list-timers --all                # Показать все таймеры и время их следующего старта
systemd-cgtop                              # Мониторинг CPU/RAM по слайсам и сервисам
```