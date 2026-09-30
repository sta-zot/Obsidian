Практика администрирования и диагностика
## Управление состоянием юнитов

```Bash
# Проверка подробного статуса (включая Cgroup и последние строки логов)
systemctl status myapp.service

# Бесперебойный перезапуск конфигурации без остановки процессов (если поддерживает сервис)
systemctl reload myapp.service

# Просмотр дерева Cgroups и занимаемых ресурсов сервисами в реальном времени
systemd-cgtop

# Анализ времени загрузки юнитов при старте системы
systemd-analyze blame
systemd-analyze critical-chain
```
## Работа с логами через Journalctl

```Bash
# Логи конкретного сервиса в реальном времени
journalctl -u myapp.service -f

# Логи сервиса за текущую загрузку
journalctl -u myapp.service -b

# Логи в формате JSON для интеграции с SIEM/Loki
journalctl -u myapp.service -o json-pretty -n 20
```
## Быстрая проверка и тестирование ресурсов на лету
Создание временного юнита со сниженным приоритетом и ограничением памяти без создания `.service` файла:

```Bash
systemd-run --scope -p MemoryMax=500M -p CPUWeight=20 /usr/bin/stress-ng --vm 2 --vm-bytes 1G
```
### Чек-лист для отладки конфигураций
1. Проверяйте синтаксис файлов перед перезапуском:
```Bash
    systemd-analyze verify /etc/systemd/system/myapp.service
```

2. Всегда выполняйте `sudo systemctl daemon-reload` после внесения любых изменений в файлы юнитов на диске.
3. Если сервис не заводится из-за ограничений прав, проверяйте SELinux/AppArmor или параметры секции `[Service]` (`ReadWritePaths`, `ProtectSystem`).

## Глубокое погружение в логи
Демон `journald` собирает `stdout`/`stderr` всех процессов, а также сообщения ядра (kmsg), audit-события и сигналы cgroups.
```bash
# 1. Логи конкретного сервиса в реальном времени (режим tail -f)
journalctl -u myapp.service -f

# 2. Логи сервиса строго с момента последней загрузки системы
journalctl -u myapp.service -b

# 3. Логи за конкретный временной интервал
journalctl -u myapp.service --since "2026-09-30 00:00:00" --until "2026-09-30 08:00:00"

# 4. Логи с уровнем ошибок и выше (Priority: err, crit, alert, emerg)
journalctl -u myapp.service -p err..emerg

# 5. Вывод в формате JSON с полным набором метаданных (PID, Cgroup, SELinux context, UID)
journalctl -u myapp.service -o json-pretty -n 5

# 6. Логи конкретного процесса по его PID
journalctl _PID=12345
```

### Инспекция и проверка синтаксиса
Перед запуском или перезагрузкой демона важно убедиться, что в конфигурации нет ошибок.
#### Валидация юнитов (`systemd-analyze verify`)
Проверяет синтаксические ошибки, несуществующие пути и конфликтующие директивы в файлах юнитов:
```Bash
systemd-analyze verify /etc/systemd/system/myapp.service
```
#### Анализ итоговой конфигурации (`systemctl show`)
Показывает полные рассчитанные параметры юнита (включая дефолты и примененные drop-in файлы):
```Bash
# Показать ВСЕ параметры юнита
systemctl show myapp.service

# Посмотреть конкретный параметр (например, лимиты памяти и статус перезапуска)
systemctl show myapp.service -p MemoryMax -p Restart -p FragmentPath
```
### Анализ производительности и графиков загрузки
Если сервис медленно запускается или блокирует цепочку старта системы:
#### `systemd-analyze blame`
Выводит список всех юнитов, отсортированный по времени их инициализации:
```Bash
systemd-analyze blame
```
#### `systemd-analyze critical-chain`
Строит древовидную цепочку сервисов, критичных по времени запуска (показывает, какой именно юнит задерживает старт остальных):
```Bash
systemd-analyze critical-chain myapp.service
```
#### Отладка падений: Core Dumps (`systemd-coredump`)
При краше процесса (Segmentation fault, Abort) systemd автоматически перехватывает дамп памяти ядра и сохраняет его с метаданными.
```Bash
# Посмотреть список всех зафиксированных падений процессов
coredumpctl list

# Посмотреть подробную информацию о последнем краше конкретного сервиса
coredumpctl info myapp.service

# Открыть дамп памяти прямо в отладчике GDB
coredumpctl gdb myapp.service
```
### Мониторинг Cgroups и ресурсов
```Bash
# Мониторинг потребления CPU, RAM, IO и PIDs в стиле htop
systemd-cgtop

# Дерево всех запущенных cgroups и процессов внутри них
systemd-cgls
```
### Режим суперотладки (Debug Logging systemd)
Если сам systemd ведет себя непонятно (не срабатывают зависимости, не запускаются таргеты), можно перевести менеджер процессов в режим подробного логгирования прямо на лету:
```bash
# Включить debug-логирование самого PID 1
sudo systemd-analyze log-level debug

# Смотреть отладочный вывод системного менеджера
journalctl -f -u systemd

# Вернуть уровень логов по умолчанию
sudo systemd-analyze log-level info
```

## Сводная шпаргалка по утилитам отладки

| **Утилита**                  | **Для чего используется**                                  |
| ---------------------------- | ---------------------------------------------------------- |
| **`journalctl`**             | Чтение и фильтрация логов процессов и системы.             |
| **`systemd-analyze verify`** | Проверка синтаксиса `.service`, `.timer`, `.slice` файлов. |
| **`systemd-analyze blame`**  | Поиск сервисов, замедляющих загрузку.                      |
| **`systemctl show`**         | Просмотр итоговых переменных и настроек cgroups юнита.     |
| **`coredumpctl`**            | Анализ аварийных дампов памяти (Segfaults/Crash).          |
| **`systemd-cgtop`**          | Мониторинг ресурсов процессов в разрезе Slices/Services.   |
