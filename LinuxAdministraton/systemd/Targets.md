**Systemd Targets (Таргеты)** — это логические точки группировки и синхронизации юнитов. В отличие от классических уровней выполнения SysVinit (Runlevels), таргеты могут выполняться **параллельно**, включать друг друга и образовывать гибкие графы зависимостей.

Таргеты не содержат команд запуска — они состоят из набора связей (`Wants=`, `Requires=`, `After=`, `Before=`) с сервисами, сокетами, таймерами и другими таргетами.
## 1. Сравнение: SysVinit Runlevels vs. systemd Targets

В старой системе SysVinit загрузка происходила строго линейно и монопольно: система могла находиться строго на одном уровне (от 0 до 6). В systemd уровни выполнения сохранены только ради обратной совместимости через символические ссылки.

| **Параметр**                | **SysVinit Runlevels**                                             | **systemd Targets**                                                                                                         |
| --------------------------- | ------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------- |
| **Структура**               | Числовые уровни (`0`, `1`, `3`, `5`, `6`)                          | Декларативные текстовые файлы (`.target`)                                                                                   |
| **Запуск**                  | Строго последовательный запуск скриптов `/etc/rcX.d/S*`            | Вычисление графа зависимостей и **максимально параллельный запуск**                                                         |
| **Состояние**               | Система находится ровно на **одному** уровне в один момент времени | Несколько таргетов могут быть **активны одновременно** (например, `network.target` + `multi-user.target` + `timers.target`) |
| **Изоляция / Переключение** | Переключение сбросом сценария `init X`                             | Переключение изолирующими таргетами (`systemctl isolate`)                                                                   |
### Таблица соответствий (Compatibility Mapping)

| **Старый Runlevel** | **Эквивалентный systemd Target** | **Назначение**                                                                                |
| ------------------- | -------------------------------- | --------------------------------------------------------------------------------------------- |
| **0**               | `poweroff.target`                | Выключение системы.                                                                           |
| **1 (S)**           | `rescue.target`                  | Однопользовательский режим восстановления (монтирование root в read-only, запуск root shell). |
| **2, 3, 4**         | `multi-user.target`              | Многопользовательский текстовый режим с сетью (стандартный серверный режим).                  |
| **5**               | `graphical.target`               | Многопользовательский режим с графической оболочкой (X11/Wayland + Display Manager).          |
| **6**               | `reboot.target`                  | Перезагрузка системы.                                                                         |
| **—**               | `emergency.target`               | Экстренный режим (минимальный shell, система не монтирует диски из `fstab`).                  |
## 2. Ключевые системные таргеты и Цепочка загрузки
Загрузка Linux под управлением systemd — это направленный бесконтурный граф (DAG). Каждая стадия загрузки представлена отдельным таргетом.
```Plaintext
sysinit.target
  ├── basic.target
  │    ├── multi-user.target
  │    │    └── graphical.target
  │    └── network.target
  └── sockets.target
```
### Основные вехи загрузки:
1. **`sysinit.target`** — Инициализация системы: монтирование виртуальных файловых систем (`/proc`, `/sys`), активация Swap, настройка системного времени и загрузка драйверов ядра. 
2. **`basic.target`** — Базовая готовность: монтирование всех локальных дисков из `/etc/fstab`, запуск базовых сокетов, таймеров и подсистем безопасности.
3. **`network.target`** — Индикация запуска сетевого стека (поддержка интерфейсов).
4. **`network-online.target`** — Индикация того, что сеть **реально поднята и получила IP-адрес** (важно для сервисов, привязывающихся к конкретным IP).
5. **`multi-user.target`** — Готовая консольная операционная система (запущены все пользовательские демоны, SSH, СУБД).
6. **`graphical.target`** — Запуск GUI (дисплейный менеджер GDM/LightDM).
## 3. Анатомия `.target` файла
Таргет-файл хранится в `/etc/systemd/system/` или `/lib/systemd/system/`. В нём **нет секции `[Service]`**
```TOML
[Unit]
Description=My Custom Application Stack Target
Documentation=https://docs.internal/architecture

# Отрабатывает строго ПОСЛЕ того, как поднимется базовая система и сеть
After=multi-user.target network-online.target
Wants=network-online.target

# Если этот таргет изолируется (systemctl isolate), останавливать другие неизолируемые сервисы
AllowIsolate=true
```
### Как формируются связи с сервисами?
Связи таргета с сервисами задаются двумя способами:
1. **Декларативно в сервисах (`[Install]`):**
    Когда в `myapp.service` написано `WantedBy=multi-user.target`, команда `systemctl enable myapp.service` создает симлинк:
    `/etc/systemd/system/multi-user.target.wants/myapp.service -> /etc/systemd/system/myapp.service`
2. **Декларативно в самом тагрете (Директивы `Wants=` / `Requires=`):**
    Вы можете прямо в `.target` файле перечислить нужные сервисы.
## 4. Практика: Создание собственного кастомного Таргета
Представьте сценарий: у вас есть комплекс сервисов аналитики (`analytics-ingest.service`, `analytics-worker.service`, `analytics-db.service`). Вы хотите управлять ими как **единым целым** (включать, выключать и переключать систему в «режим аналитики»).
### Шаг 1: Создаем файл таргета `/etc/systemd/system/analytics.target`

```TOML
[Unit]
Description=Analytics Processing Cluster Target
Documentation=https://wiki.internal/ops/analytics

# Запускаться строго после основной системы
After=multi-user.target
Wants=multi-user.target

# Мягкие зависимости на сервисы входящие в таргет
Wants=analytics-db.service analytics-ingest.service analytics-worker.service

# Разрешить переключение в этот таргет через isolate
AllowIsolate=true

[Install]
WantedBy=multi-user.target
```

### Шаг 2: Привязываем сервисы к нашему таргету
В файле сервиса `/etc/systemd/system/analytics-worker.service`:
```TOML
[Unit]
Description=Analytics Worker Process
After=analytics-db.service
Requires=analytics-db.service

[Service]
ExecStart=/opt/analytics/bin/worker

[Install]
# При включении сервиса он будет привязываться к нашему кастомному таргету!
WantedBy=analytics.target
```
### Шаг 3: Активация и управление

```Bash
# 1. Перечитаем конфигурацию
sudo systemctl daemon-reload

# 2. Включим автозапуск таргета
sudo systemctl enable analytics.target

# 3. Запустим ВСЮ группу сервисов аналитики одной командой
sudo systemctl start analytics.target

# 4. Проверим статус таргета и входящих в него юнитов
systemctl status analytics.target

# 5. Остановим ВСЮ группу сервисов одновременно
sudo systemctl stop analytics.target
```
## 5. Управление целями и переключение таргетов
### Просмотр и смена таргета по умолчанию (Default Target)
Таргет по умолчанию — это состояние, в которое система загружается при включении сервера.
```Bash
# Узнать текущий таргет по умолчанию (обычно multi-user.target или graphical.target)
systemctl get-default

# Изменить таргет по умолчанию на текстовый серверный режим
sudo systemctl set-default multi-user.target

# Изменить таргет по умолчанию на графический режим
sudo systemctl set-default graphical.target
```
### Переключение состояния системы «на лету» (`systemctl isolate`)
Команда `isolate` переводит систему в выбранный таргет, **останавливая все сервисы, которые не привязаны к целевому таргету**. _(Работает только если у целевого таргета указано `AllowIsolate=true`)._
```Bash
# Перевести сервер в режим восстановления (закроет все пользовательские процессы)
sudo systemctl isolate rescue.target

# Перевести систему из графического режима в текстовый консольный
sudo systemctl isolate multi-user.target

# Вернуться в нормальный режим
sudo systemctl isolate default.target
```
## Сводная шпаргалка по командам работы с Targets

| **Команда**                                   | **Описание**                                                                     |
| --------------------------------------------- | -------------------------------------------------------------------------------- |
| **`systemctl list-units --type=target`**      | Показать все активные в данный момент таргеты.                                   |
| **`systemctl list-unit-files --type=target`** | Показать все установленные в системе таргеты.                                    |
| **`systemctl get-default`**                   | Показать таргет по умолчанию при загрузке.                                       |
| **`systemctl set-default <target>`**          | Установить таргет по умолчанию (`multi-user.target` / `graphical.target`).       |
| **`systemctl isolate <target>`**              | Мгновенно переключить систему в указанный таргет со сбросом сторонних процессов. |
