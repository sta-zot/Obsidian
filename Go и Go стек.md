## Оглавление по урокам

1. [Вводная лекция](#1-%D0%B2%D0%B2%D0%BE%D0%B4%D0%BD%D0%B0%D1%8F-%D0%BB%D0%B5%D0%BA%D1%86%D0%B8%D1%8F)
2. [Компилятор Go, работа с пакетами (модулями)](#2-%D0%BA%D0%BE%D0%BC%D0%BF%D0%B8%D0%BB%D1%8F%D1%82%D0%BE%D1%80-go-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0-%D1%81-%D0%BF%D0%B0%D0%BA%D0%B5%D1%82%D0%B0%D0%BC%D0%B8-%D0%BC%D0%BE%D0%B4%D1%83%D0%BB%D1%8F%D0%BC%D0%B8)
3. [Приватные модули, массивы, устройство слайсов](#3-%D0%BF%D1%80%D0%B8%D0%B2%D0%B0%D1%82%D0%BD%D1%8B%D0%B5-%D0%BC%D0%BE%D0%B4%D1%83%D0%BB%D0%B8-%D0%BC%D0%B0%D1%81%D1%81%D0%B8%D0%B2%D1%8B-%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2%D0%BE-%D1%81%D0%BB%D0%B0%D0%B9%D1%81%D0%BE%D0%B2)
4. [Условные конструкции, циклы, структуры, методы, функции](#4-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%BD%D1%8B%D0%B5-%D0%BA%D0%BE%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8-%D1%86%D0%B8%D0%BA%D0%BB%D1%8B-%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%82%D1%83%D1%80%D1%8B-%D0%BC%D0%B5%D1%82%D0%BE%D0%B4%D1%8B-%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%B8)
5. [Функции как тип, анонимные функции и замыкания. Указатели](#5-%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%B8-%D0%BA%D0%B0%D0%BA-%D1%82%D0%B8%D0%BF-%D0%B0%D0%BD%D0%BE%D0%BD%D0%B8%D0%BC%D0%BD%D1%8B%D0%B5-%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%B8-%D0%B8-%D0%B7%D0%B0%D0%BC%D1%8B%D0%BA%D0%B0%D0%BD%D0%B8%D1%8F-%D1%83%D0%BA%D0%B0%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D0%B8)
6. [Слайсы. Задачи на указатели](#6-%D1%81%D0%BB%D0%B0%D0%B9%D1%81%D1%8B-%D0%B7%D0%B0%D0%B4%D0%B0%D1%87%D0%B8-%D0%BD%D0%B0-%D1%83%D0%BA%D0%B0%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D0%B8)
7. [Замыкания. Append в слайсах. Мапы до и после go 1.24](#7-%D0%B7%D0%B0%D0%BC%D1%8B%D0%BA%D0%B0%D0%BD%D0%B8%D1%8F-append-%D0%B2-%D1%81%D0%BB%D0%B0%D0%B9%D1%81%D0%B0%D1%85-%D0%BC%D0%B0%D0%BF%D1%8B-%D0%B4%D0%BE-%D0%B8-%D0%BF%D0%BE%D1%81%D0%BB%D0%B5-go-124)
8. [Решение задач на слайсы. Горутины, планировщик в Go](#8-%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B7%D0%B0%D0%B4%D0%B0%D1%87-%D0%BD%D0%B0-%D1%81%D0%BB%D0%B0%D0%B9%D1%81%D1%8B-%D0%B3%D0%BE%D1%80%D1%83%D1%82%D0%B8%D0%BD%D1%8B-%D0%BF%D0%BB%D0%B0%D0%BD%D0%B8%D1%80%D0%BE%D0%B2%D1%89%D0%B8%D0%BA-%D0%B2-go)
9. [Интерфейсы](#9-%D0%B8%D0%BD%D1%82%D0%B5%D1%80%D1%84%D0%B5%D0%B9%D1%81%D1%8B)
10. [Ресиверы методов. Горутины. Каналы](#10-%D1%80%D0%B5%D1%81%D0%B8%D0%B2%D0%B5%D1%80%D1%8B-%D0%BC%D0%B5%D1%82%D0%BE%D0%B4%D0%BE%D0%B2-%D0%B3%D0%BE%D1%80%D1%83%D1%82%D0%B8%D0%BD%D1%8B-%D0%BA%D0%B0%D0%BD%D0%B0%D0%BB%D1%8B)
11. [Горутины и каналы](#11-%D0%B3%D0%BE%D1%80%D1%83%D1%82%D0%B8%D0%BD%D1%8B-%D0%B8-%D0%BA%D0%B0%D0%BD%D0%B0%D0%BB%D1%8B)
12. [Docker и Kubernetes](#12-docker-%D0%B8-kubernetes)
13. [Kubernetes. k3d](#13-kubernetes-k3d)
14. [Архитектура проекта](#14-%D0%B0%D1%80%D1%85%D0%B8%D1%82%D0%B5%D0%BA%D1%82%D1%83%D1%80%D0%B0-%D0%BF%D1%80%D0%BE%D0%B5%D0%BA%D1%82%D0%B0)
15. [Обзор реального проекта с БД](#15-%D0%BE%D0%B1%D0%B7%D0%BE%D1%80-%D1%80%D0%B5%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D0%B3%D0%BE-%D0%BF%D1%80%D0%BE%D0%B5%D0%BA%D1%82%D0%B0-%D1%81-%D0%B1%D0%B4)
16. [HTTP сервер и клиент, роутер и мидлвары, интеграционные тесты](#16-http-%D1%81%D0%B5%D1%80%D0%B2%D0%B5%D1%80-%D0%B8-%D0%BA%D0%BB%D0%B8%D0%B5%D0%BD%D1%82-%D1%80%D0%BE%D1%83%D1%82%D0%B5%D1%80-%D0%B8-%D0%BC%D0%B8%D0%B4%D0%BB%D0%B2%D0%B0%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%BE%D0%BD%D0%BD%D1%8B%D0%B5-%D1%82%D0%B5%D1%81%D1%82%D1%8B)
17. [Работа с ошибками. Логгер. Контекст](#17-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0-%D1%81-%D0%BE%D1%88%D0%B8%D0%B1%D0%BA%D0%B0%D0%BC%D0%B8-%D0%BB%D0%BE%D0%B3%D0%B3%D0%B5%D1%80-%D0%BA%D0%BE%D0%BD%D1%82%D0%B5%D0%BA%D1%81%D1%82)
18. [Option, Config. Работа с Postgres, миграции](#18-option-config-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0-%D1%81-postgres-%D0%BC%D0%B8%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8)
19. [SpecFirst подход. Генерация сервера и клиента по OpenAPI. Тестирование. Моки](#19-specfirst-%D0%BF%D0%BE%D0%B4%D1%85%D0%BE%D0%B4-%D0%B3%D0%B5%D0%BD%D0%B5%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D1%81%D0%B5%D1%80%D0%B2%D0%B5%D1%80%D0%B0-%D0%B8-%D0%BA%D0%BB%D0%B8%D0%B5%D0%BD%D1%82%D0%B0-%D0%BF%D0%BE-openapi-%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BC%D0%BE%D0%BA%D0%B8)
20. [GRPC. Генерация сервера и клиента по proto файлу](#20-grpc-%D0%B3%D0%B5%D0%BD%D0%B5%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D1%81%D0%B5%D1%80%D0%B2%D0%B5%D1%80%D0%B0-%D0%B8-%D0%BA%D0%BB%D0%B8%D0%B5%D0%BD%D1%82%D0%B0-%D0%BF%D0%BE-proto-%D1%84%D0%B0%D0%B9%D0%BB%D1%83)
21. [Kafka](#21-kafka)
22. [Kafka. Transactional Outbox pattern, S3](#22-kafka-transactional-outbox-pattern-s3)
23. [Redis. Observability. Метрики, Prometheus и Grafana](#23-redis-observability-%D0%BC%D0%B5%D1%82%D1%80%D0%B8%D0%BA%D0%B8-prometheus-%D0%B8-grafana)
24. [Логи. Трейсинг. Бенчмарки. Профилирование. Линтеры](#24-%D0%BB%D0%BE%D0%B3%D0%B8-%D1%82%D1%80%D0%B5%D0%B9%D1%81%D0%B8%D0%BD%D0%B3-%D0%B1%D0%B5%D0%BD%D1%87%D0%BC%D0%B0%D1%80%D0%BA%D0%B8-%D0%BF%D1%80%D0%BE%D1%84%D0%B8%D0%BB%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BB%D0%B8%D0%BD%D1%82%D0%B5%D1%80%D1%8B)

Бонус: [Техническое собеседование в Тиньков, 1 этап](#%D0%B1%D0%BE%D0%BD%D1%83%D1%81-%D1%82%D0%B5%D1%85%D0%BD%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B5-%D1%81%D0%BE%D0%B1%D0%B5%D1%81%D0%B5%D0%B4%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B2-%D1%82%D0%B8%D0%BD%D1%8C%D0%BA%D0%BE%D0%B2-1-%D1%8D%D1%82%D0%B0%D0%BF)

## 1. Вводная лекция

Запись: [https://disk.yandex.ru/d/-cwKCe0m1wv-Uw](https://disk.yandex.ru/d/-cwKCe0m1wv-Uw)

Содержание:

- Как построен этот курс
- О языке Go
- Сравнение с другими языками
- Зарплата Go разработчика в РФ
- Как выглядит собеседование

Материалы:

- Работа с OpenAI из кода: [https://github.com/golang-school/potok-2-example](https://github.com/golang-school/potok-2-example)
- Пример проекта с несколькими доменами: [https://github.com/golang-school/layout](https://github.com/golang-school/layout)

ДЗ:

- Пройти Go tour (без задач): [https://go.dev/tour/welcome/1](https://go.dev/tour/welcome/1)

## 2. Компилятор Go, работа с пакетами (модулями)

Запись: [https://disk.yandex.ru/d/39490JadNqXWAg](https://disk.yandex.ru/d/39490JadNqXWAg)

Содержание:

- Основные команды компилятора
- Импорты
- Работа со своими и сторонними пакетами (они же модули)

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-2](https://gitlab.golang-school.ru/potok-2/lessons/lesson-2)

ДЗ:

- Установить компилятор Go: [https://go.dev/doc/install](https://go.dev/doc/install)
- Добиться работы команды: `go version`
- Запустить HelloWorld

## 3. Приватные модули, массивы, устройство слайсов

Запись: [https://disk.yandex.ru/d/59shntDQRM9sVg](https://disk.yandex.ru/d/59shntDQRM9sVg)

Содержание:

- Работа с приватными модулями
- Беглый обзор синтаксиса:
    - Константы, арифметика, сравнение на равенство
- Про затенение переменных
- Про массивы
- Про внутреннее устройство слайса (он же динамический массив, срез, slice)

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-3](https://gitlab.golang-school.ru/potok-2/lessons/lesson-3)

ДЗ:

- Написать fizzbuzz на Go: [https://gitlab.golang-school.ru/potok-2/lessons/lesson-3/-/blob/main/home_work.md](https://gitlab.golang-school.ru/potok-2/lessons/lesson-3/-/blob/main/home_work.md)

## 4. Условные конструкции, циклы, структуры, методы, функции

Запись: [https://disk.yandex.ru/d/659xlUTEj6T7GA](https://disk.yandex.ru/d/659xlUTEj6T7GA)

Содержание:

- Бегло про синтаксис:
    - If, switch, for
- Структуры и методы
- Padding (выравнивание) структур
- Embedding (встраивание) vs Composition (композиция)
- Функции, сигнатуры, возвращаемые значения
- Типизированый int и string

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-4](https://gitlab.golang-school.ru/potok-2/lessons/lesson-4)

ДЗ:

- Посмотреть про выравнивание структур: [https://youtu.be/fSrXheYgmTg](https://youtu.be/fSrXheYgmTg)
- Почитать: [https://habr.com/ru/companies/vk/articles/314804/](https://habr.com/ru/companies/vk/articles/314804/) (примеры из статьи лучше запускать в IDE)

## 5. Функции как тип, анонимные функции и замыкания. Указатели

Запись: [https://disk.yandex.ru/d/eDm_BRo1vD8kxw](https://disk.yandex.ru/d/eDm_BRo1vD8kxw)

Содержание:

- Функция как тип
- Функция как аргумент
- Функция как возвращаемое значение
- Анонимна функция синхронная и асинхронная
- Замыкания
- Указатели
- Разница между указателем и значением

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-5](https://gitlab.golang-school.ru/potok-2/lessons/lesson-5)

ДЗ:

- Если хотите, можете порешать задачи: [https://gitlab.golang-school.ru/potok-2/lessons/lesson-5/-/tree/main/tasks](https://gitlab.golang-school.ru/potok-2/lessons/lesson-5/-/tree/main/tasks)

## 6. Слайсы. Задачи на указатели

Запись: [https://disk.yandex.ru/d/FJCvFzZjZfBzjA](https://disk.yandex.ru/d/FJCvFzZjZfBzjA)

Содержание:

- Разбор задач на указатели
- Что такое слайс
- Как выглядят слайсы на низком уровне
- Какие есть возможности у слайсов
- Создание, чтение, изменение, копирование слайсов

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-6](https://gitlab.golang-school.ru/potok-2/lessons/lesson-6)

ДЗ:

- Почитать: [https://habr.com/ru/articles/739754/](https://habr.com/ru/articles/739754/)
- Посмотреть: [https://youtu.be/7ij3u-0YsJI](https://youtu.be/7ij3u-0YsJI)

## 7. Замыкания. Append в слайсах. Мапы до и после go 1.24

Запись: [https://disk.yandex.ru/d/ObTRQ4Gyyjo2RA](https://disk.yandex.ru/d/ObTRQ4Gyyjo2RA)

Содержание:

- Как устроено замыкание
- Append в слайсах
- Работа с мапами
- Мапы до go 1.24 - закрытая адресация, бакеты
- Мапы после go 1.24 - открытая адресация, SIMD оптимизация при поиске

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-7](https://gitlab.golang-school.ru/potok-2/lessons/lesson-7)

ДЗ:

- Посмотреть обязательно, хоть через силу (если хотя бы 10% поймёте, это успех):
    - Красиво высмеивает новую реализацию [https://youtu.be/CTe3mQAm3Eo](https://youtu.be/CTe3mQAm3Eo)
    - Хорошо разбирается в мапах [https://youtu.be/fU88jd0Q0Dk](https://youtu.be/fU88jd0Q0Dk)
- Не обязательно, но если хотите ещё что-то посмотреть:
    - Николай Тузов про старые мапы [https://youtu.be/P_SXTUiA-9Y](https://youtu.be/P_SXTUiA-9Y)
    - Владимир Балун про старые мапы [https://youtu.be/_EzbLVvao7c](https://youtu.be/_EzbLVvao7c)
    - Олег Козырев про старые и новые мапы [https://youtu.be/lfeOR6zDnx4](https://youtu.be/lfeOR6zDnx4)

## 8. Решение задач на слайсы. Горутины, планировщик в Go

Запись: [https://disk.yandex.ru/d/4nsCAp4gFpBHQA](https://disk.yandex.ru/d/4nsCAp4gFpBHQA)

Содержание:

- Разбор задач на слайсы
- Планировщик в Linux - вытесняющая многозадачность
- Планировщик в Go - кооперативно-вытесняющая многозадачность
- GMP модель:
    - G Goroutine - единица выполнения в Go
    - M Maschine - по сути тоже самое что Thread (единица выполнения в ОС)
    - P Processor - локальная очередь Goroutine
- Функция main - тоже горутина
- runtime.GOMAXPROCS() - можно указать сколько потоков ОС будет работать одновременно
- runtime.Gosched() - аналог await, отдаёт управление планировщику (не используется в реальном коде)

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-8](https://gitlab.golang-school.ru/potok-2/lessons/lesson-8)

ДЗ:

- Представьте что вам предстоит собеседовать Go разработчика:
    
    - Придумайте 2 задачи (лёгкую и сложную) на слайсы и гонку данных в слайсах
    - Собеседующему нужно ответить на вопрос: "что выведет этот код", либо "что нужно изменить, чтобы заработало"
    - Задачи должны быть с подвохом, чтобы отличить junior от middle
    - Добавьте свои задачи в репозиторий: [https://gitlab.golang-school.ru/potok-2/lessons/slice-task](https://gitlab.golang-school.ru/potok-2/lessons/slice-task)
- Не обязательно, но если что-то из этого посмотрите, будет хорошо:
    
    - [https://youtu.be/EjgD9cLCYsM](https://youtu.be/EjgD9cLCYsM)
    - Николай Тузов [https://youtu.be/kedW1xO3Zbo](https://youtu.be/kedW1xO3Zbo)
    - Владимир Балун [https://youtu.be/P2Tzdg8n9hw](https://youtu.be/P2Tzdg8n9hw)
    - Ещё Балун [https://www.youtube.com/live/uU0FbA3u5vI](https://www.youtube.com/live/uU0FbA3u5vI)
    - Олег Козырев [https://youtu.be/8z6FAaNPA-M](https://youtu.be/8z6FAaNPA-M)
    - На индийском английском [https://youtu.be/wQpC99Xu1U4](https://youtu.be/wQpC99Xu1U4)

## 9. Интерфейсы

Запись: [https://disk.yandex.ru/d/IcFkGc98lhIHbA](https://disk.yandex.ru/d/IcFkGc98lhIHbA)

Содержание:

- Что такое интерфейсы
- Как они устроены на низком уровне
- Композиция интерфейсов
- Типизированный nil (когда в интерфейсе nil != nil)
- Пустой интерфейс
- Приведение типов (type assertion)
- Type switch

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-9](https://gitlab.golang-school.ru/potok-2/lessons/lesson-9)

ДЗ:

- Хороших материалов по интерфейсам нет, но если хотите что-то почитать/посмотреть:
    - Хабр [https://habr.com/ru/articles/856272/](https://habr.com/ru/articles/856272/)
    - Хабр [https://habr.com/ru/companies/vk/articles/463063/](https://habr.com/ru/companies/vk/articles/463063/)
    - Тузов [https://youtu.be/eYHCCht8eX4](https://youtu.be/eYHCCht8eX4)
    - В ютубе по запросу `интерфейсы в golang` очень много видосов одинаковой степени унылости.
    - И не расстраиваетесь если плохо понимаете интерфейсы, это нормально, у всех так было.

## 10. Ресиверы методов. Горутины. Каналы

Запись: [https://disk.yandex.ru/d/o-cW42ZxEeZ1yg](https://disk.yandex.ru/d/o-cW42ZxEeZ1yg)

Содержание:

- Ресиверы методов по указателю и значению
- Горутины и гонка данных
- Mutex, Atomic, WaitGroup, Once
- Каналы с буфером и без буфера
- Закрытие каналов
- Select

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-10](https://gitlab.golang-school.ru/potok-2/lessons/lesson-10)

ДЗ:

- Если интересно, статья про ресиверы у методов: [https://gronskiy.com/posts/2020-04-golang-pointer-vs-value-methods/](https://gronskiy.com/posts/2020-04-golang-pointer-vs-value-methods/)
- Почитать: [https://habr.com/ru/articles/308070/](https://habr.com/ru/articles/308070/)
- Посмотреть: [https://youtu.be/Tp5xhTMFuLU?si=5JLcRiXSSRJpMCYm](https://youtu.be/Tp5xhTMFuLU?si=5JLcRiXSSRJpMCYm)
- Тузов про каналы: [https://youtu.be/8NhcDt1BCmc?si=v1SF8HW2C06tOVnn](https://youtu.be/8NhcDt1BCmc?si=v1SF8HW2C06tOVnn)
- Если есть время и интересно: [https://habr.com/ru/articles/490336/](https://habr.com/ru/articles/490336/)

## 11. Горутины и каналы

Запись: [https://disk.yandex.ru/d/L7nE8FdLE2UH3Q](https://disk.yandex.ru/d/L7nE8FdLE2UH3Q)

Содержание:

- Работа с буферизированными и небуферизированными каналами
- Закрытие каналов
- Gracefull shutdown
- Таймауты и дедлайны

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-11](https://gitlab.golang-school.ru/potok-2/lessons/lesson-11)

ДЗ:

- Очень важно покрутить примеры из материалов урока с каналами. Поиграться с буфером и закрытием каналов.
- Must have! Визуализация работы горутин [https://habr.com/ru/articles/276255/](https://habr.com/ru/articles/276255/)
- Если интересно и есть время: внутреннее устройство мьютексов [https://youtu.be/h6-Jiohy1Ak?si=N8RmYs9eQg0nJHP5](https://youtu.be/h6-Jiohy1Ak?si=N8RmYs9eQg0nJHP5)

## 12. Docker и Kubernetes

Запись: [https://disk.yandex.ru/d/KlxaqLt_TwgC_g](https://disk.yandex.ru/d/KlxaqLt_TwgC_g)

Содержание:

- Что такое контейнеры и зачем они нужны
- Основные команды docker
- Работа с Docker Hub и Gitlab Container Registry
- Что такое Kubernetes и зачем он нужен
- Основные манифесты Kubernetes

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-12](https://gitlab.golang-school.ru/potok-2/lessons/lesson-12)

ДЗ:

- Установить Docker
- Повторить команды из урока: [https://gitlab.golang-school.ru/potok-2/lessons/lesson-12/-/tree/main/4-docker](https://gitlab.golang-school.ru/potok-2/lessons/lesson-12/-/tree/main/4-docker)
- Научится делать команды login, push, pull
- Запустить приложение локально и в контейнере по инструкции в readme [https://gitlab.golang-school.ru/potok-2/lessons/lesson-12/-/tree/main/5-docker-file](https://gitlab.golang-school.ru/potok-2/lessons/lesson-12/-/tree/main/5-docker-file)
- Запустить контейнер с помощью `docker compose`
- Если не сталкивались с docker'ом посмотрите что-нибудь на ютубе, там полно видео на эту тему

## 13. Kubernetes. k3d

Запись: [https://disk.yandex.ru/d/wHz68iLj5UGFCA](https://disk.yandex.ru/d/wHz68iLj5UGFCA)

Содержание:

- Запуск приложения в docker compose
- Makefile
- Установка k3d
- Запуск локального кластера k3d
- Основные команды kubectl
- Деплой приложения в локальный кластер
- Деплой приложения в удалённый кластер с помощью CI/CD
- .gitlab-ci.yml - CI/CD в Gitlab
- Базовые манифесты Kubernetes

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-13](https://gitlab.golang-school.ru/potok-2/lessons/lesson-13)

ДЗ:

- Сделать копию папки mnepryakhin-my-app и переименовать (`свой логин + название репозитория`) в репозитории [https://gitlab.golang-school.ru/potok-2/deploy](https://gitlab.golang-school.ru/potok-2/deploy)
    - Заменить `mnepryakhin` на свой логин во всех файлах своей новой папки
    - Запушить изменения
- Скопировать репозиторий в свою папку [https://gitlab.golang-school.ru/potok-2/mnepryakhin/my-app](https://gitlab.golang-school.ru/potok-2/mnepryakhin/my-app)
    - Заменить `mnepryakhin` на свой логин [https://gitlab.golang-school.ru/potok-2/mnepryakhin/my-app/-/blob/main/cmd/app/main.go](https://gitlab.golang-school.ru/potok-2/mnepryakhin/my-app/-/blob/main/cmd/app/main.go)
    - И здесь тоже заменить [https://gitlab.golang-school.ru/potok-2/mnepryakhin/my-app/-/blob/main/.gitlab-ci.yml](https://gitlab.golang-school.ru/potok-2/mnepryakhin/my-app/-/blob/main/.gitlab-ci.yml)
    - Запушить изменения
    - На странице с пайплайнами убедится что всё зеленое ([https://gitlab.golang-school.ru/potok-2/mnepryakhin/my-app/-/pipelines](https://gitlab.golang-school.ru/potok-2/mnepryakhin/my-app/-/pipelines))
    - Убедится что бот изменил тег образа: [https://gitlab.golang-school.ru/potok-2/deploy/-/commits/main](https://gitlab.golang-school.ru/potok-2/deploy/-/commits/main)
    - Проверить что приложение открывается в браузере: [http://k8s.golang-school.ru:8090/](http://k8s.golang-school.ru:8090/)/my-app

## 14. Архитектура проекта

Запись: [https://disk.yandex.ru/d/kbBI-s0br04I_Q](https://disk.yandex.ru/d/kbBI-s0br04I_Q)

Содержание:

- Слоистая архитектура
- Юзкейсы, Адаптеры, Домен
- ДТО
- Контроллеры
- Флоу выполнения запроса
- Инициализация приложения

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-14](https://gitlab.golang-school.ru/potok-2/lessons/lesson-14)

ДЗ: Если есть время и вам интересно, посмотреть:

- Хорошие картинки: [https://habr.com/ru/articles/427739/](https://habr.com/ru/articles/427739/)
- [Domain-driven design: Cамое важное](https://youtu.be/JOy_SNK3qj4?si=cS8ewH9SQNPE-fDc)
- [Чистая Архитектура и DDD 10 лет спустя](https://youtu.be/TRkqqa9MIJo?si=Kee6OYZ9qk4qy1oL)
- [Как приручить DDD](https://youtu.be/CX7RrdPgtsY?si=XzHROrowngqVBf9D)
- [DDD. Почему это правильно, и почему не работает](https://youtu.be/_Rq8t3K_YsA?si=sfuIOuaShdEINLLx)

## 15. Обзор реального проекта с БД

Запись: [https://disk.yandex.ru/d/GTscZjxDbQ7IDA](https://disk.yandex.ru/d/GTscZjxDbQ7IDA)

Содержание:

- Доменный слой
- Таблицы в БД
- Конфиг
- Инициализация приложения
- Роутинг http сервера
- Контроллеры
- Трейсинг запросов

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-15](https://gitlab.golang-school.ru/potok-2/lessons/lesson-15)

ДЗ:

- Запустить проект локально:
    - Инструкция для запуска: [https://gitlab.golang-school.ru/potok-2/lessons/lesson-15/-/blob/main/README.md](https://gitlab.golang-school.ru/potok-2/lessons/lesson-15/-/blob/main/README.md)
- Взять доку из папки api/http и попробовать сделать запросы через Postman
- Почитать код проекта, разобраться где что находится

## 16. HTTP сервер и клиент, роутер и мидлвары, интеграционные тесты

Запись: [https://disk.yandex.ru/d/AmKRo7xN77uB1A](https://disk.yandex.ru/d/AmKRo7xN77uB1A)

Содержание:

- HTTP протокол
- HTTP сервер
- Роутинг
- Мидлвары
- HTTP клиент к собственному серверу
- Интеграционные тесты

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-16](https://gitlab.golang-school.ru/potok-2/lessons/lesson-16)

ДЗ:

- Склонировать репозиторий [https://gitlab.golang-school.ru/potok-2/lessons/lesson-16](https://gitlab.golang-school.ru/potok-2/lessons/lesson-16)
- Удалить 1 из методов из контроллера, дто, юзкейса и клиента
- Написать этот метод заново (не используя Copy-Paste)
- Запустить интеграционные тесты и убедиться что всё работает

## 17. Работа с ошибками. Логгер. Контекст

Запись: [https://disk.yandex.ru/d/-IvvXdE6aEQqQQ](https://disk.yandex.ru/d/-IvvXdE6aEQqQQ)

Содержание:

- Работа с ошибками
- Добавление контекстной информации к ошибкам
- Создание своего (упрощённого) стек трейса ошибок (в одну строку) с помощью оборачивания ошибок (%w)
- Обзор логгеров
- Обзор пакета контекст (context.Context)
- Отмена операций с помощью контекста (context.Context)
- Таймауты с помощью контекста (context.Context)
- Передача контекста (context.Context) между слоями

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-17](https://gitlab.golang-school.ru/potok-2/lessons/lesson-17)

ДЗ:

- Позапускать примеры с контекстом (context.Context) [https://gitlab.golang-school.ru/potok-2/lessons/lesson-17/-/tree/main/wiki/5-context](https://gitlab.golang-school.ru/potok-2/lessons/lesson-17/-/tree/main/wiki/5-context)
- Можно почитать про контекст (context.Context) [https://habr.com/ru/companies/pt/articles/764850/](https://habr.com/ru/companies/pt/articles/764850/)

## 18. Option, Config. Работа с Postgres, миграции

Запись: [https://disk.yandex.ru/d/KQU-cTWoDcrF5A](https://disk.yandex.ru/d/KQU-cTWoDcrF5A)

Содержание:

- Паттерны Option и Config
- Обзор драйверов для работы с Postgres
- Драйвер pgx и pgx pool
- Билдер SQL запросов goqu
- Миграции с помощью migrate
- Транзакции

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-18](https://gitlab.golang-school.ru/potok-2/lessons/lesson-18)

ДЗ:

- Разобраться с миграциями:
    - Добавить миграцию
    - Откатить одну миграцию
    - Откатить все миграции
    - Применить все миграции
- Изучить и понять как работают транзакции из контекста: [https://gitlab.golang-school.ru/potok-2/lessons/lesson-18/-/tree/main/pkg/transaction](https://gitlab.golang-school.ru/potok-2/lessons/lesson-18/-/tree/main/pkg/transaction)
    - Найти место в коде, где транзакция создаётся и кладётся в контекст
    - Найти место в коде, где транзакция достаётся из контекста

## 19. SpecFirst подход. Генерация сервера и клиента по OpenAPI. Тестирование. Моки

Запись: [https://disk.yandex.ru/d/sFnq7yvZwP3UlQ](https://disk.yandex.ru/d/sFnq7yvZwP3UlQ)

Содержание:

- SpecFirst подход
- OpenAPI спецификация
- Генерация сервера и клиента
- Генерация моков с помощью mockery
- Юнит тесты

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-19](https://gitlab.golang-school.ru/potok-2/lessons/lesson-19)

ДЗ:

- Склонировать репозиторий [https://gitlab.golang-school.ru/potok-2/lessons/lesson-19](https://gitlab.golang-school.ru/potok-2/lessons/lesson-19)
- Удалить 1 из методов в контроллере
- Написать этот метод заново (не используя Copy-Paste)
- И тоже самое с клиентом [https://gitlab.golang-school.ru/potok-2/lessons/lesson-19/-/tree/main/pkg/profile_client_gen](https://gitlab.golang-school.ru/potok-2/lessons/lesson-19/-/tree/main/pkg/profile_client_gen)
    - Удалить 1 из методов в клиенте и написать заново
- Запустить интеграционные тесты и убедиться что всё работает

## 20. GRPC. Генерация сервера и клиента по proto файлу

Запись: [https://disk.yandex.ru/d/YHX0twi8LnST7g](https://disk.yandex.ru/d/YHX0twi8LnST7g)

Содержание:

- Что такое GRPC
- Разница между GRPC и REST
- Протокол Buffers (protobuf)
- Генерация сервера и клиента по proto файлу
- Интерсепторы (мидлвары) в GRPC
- Балансировка запросов между подами в REST и GRPC

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-20](https://gitlab.golang-school.ru/potok-2/lessons/lesson-20)

ДЗ:

- Запустить сервис и сделать запросы к GRPC с помощью Postman к localhost:50051
- Удалить один из методов в GRPC сервере и написать заново
- Удалить один из методов в GRPC клиенте и написать заново

## 21. Kafka

Запись: [https://disk.yandex.ru/d/BrvfAhw9fjOc2A](https://disk.yandex.ru/d/BrvfAhw9fjOc2A)

Содержание:

- Что такое Kafka
- Термины: продюсер, консьюмер, брокер, топик, партиция, сегмент, оффсет, консьюмер группа, лаг
- Отличия от RabbitMQ
- Обзор драйверов для работы с Kafka
- Стратегии записи в топик (RR по патрициям, Hashing по ключу)
- Стратегии чтения топика консьюмер группой (распределение партиций между консьюмерами): RR, Sticky, Cooperative Sticky
- Партицию можно читать от начала, от конца, с оффсета, от таймстампа
- Внутреннее устройство Kafka
- Запуск кластера из 3 брокеров в docker compose
- Что такое In Sync Replica (ISR)
- Демонстрация отключения одного из брокеров

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-21](https://gitlab.golang-school.ru/potok-2/lessons/lesson-21)

ДЗ:

- Посмотреть: [https://youtu.be/-AZOi3kP9Js](https://youtu.be/-AZOi3kP9Js)
- Можно посмотреть: [https://youtu.be/vrdNDEyrvPA](https://youtu.be/vrdNDEyrvPA)
- Можно почитать:
    - [Kafka Consumer Groups & Offsets](https://learn.conduktor.io/kafka/kafka-consumer-groups-and-consumer-offsets/)
    - [Delivery Semantics for Kafka Consumers](https://learn.conduktor.io/kafka/delivery-semantics-for-kafka-consumers/)
    - [Kafka Consumer Important Settings: Poll and Internal Threads Behavior](https://learn.conduktor.io/kafka/kafka-consumer-important-settings-poll-and-internal-threads-behavior/)

## 22. Kafka. Transactional Outbox pattern, S3

Запись: [https://disk.yandex.ru/d/sLkpuedpg5oLiw](https://disk.yandex.ru/d/sLkpuedpg5oLiw)

Содержание:

- Низкоуровневые и высокоуровневые клиенты Kafka
- Консьюмер группа на низком уровне
- Семантики доставки:
    - at most once - ни разу или один раз (если не страшны потери и нужна скорость)
    - at least once - один раз или более (если не страшны дубли, но нужна надёжность)
    - exactly once - ровно один раз (если нужны и надёжность и отсутствие дублей)
- Если не хватает скорости: асинхронный коммит оффсетов в консьюмере и асинхронный продюссер
- Примеры продюссера и консьюмера в коде приложения
- Transactional Outbox pattern и его реализация
- Бегло про S3 api
- Пример S3 адаптера в юзкейсе

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-22](https://gitlab.golang-school.ru/potok-2/lessons/lesson-22)

ДЗ:

- Покрутить примеры из урока
- Можно посмотреть:
    - [https://youtu.be/HI-XvL2FkTQ](https://youtu.be/HI-XvL2FkTQ)
    - [https://youtu.be/OnVoIAAJeOk](https://youtu.be/OnVoIAAJeOk)
    - [https://youtu.be/b42gkdta_6s](https://youtu.be/b42gkdta_6s)
    - [https://youtu.be/42rFNjztbOM](https://youtu.be/42rFNjztbOM)
- Можно почитать [https://habr.com/ru/companies/lamoda/articles/678932/](https://habr.com/ru/companies/lamoda/articles/678932/)

## Бонус: Техническое собеседование в Тиньков, 1 этап

Запись: [https://disk.yandex.ru/i/6Ede7dD_4dtcPg](https://disk.yandex.ru/i/6Ede7dD_4dtcPg)

Решение задач:

- Слайсы
- Указатели
- Горутины
- Каналы
- Вейт группа
- Контекст

## 23. Redis. Observability. Метрики, Prometheus и Grafana

Запись: [https://disk.yandex.ru/d/GA1yu5Su_KTMMw](https://disk.yandex.ru/d/GA1yu5Su_KTMMw)

Содержание:

- Обзор Redis
- Использование адаптера Redis в юзкейсе update profile
- Обзор ручки get profiles
- Observability - метрики, логи, трейсы
- Ручка /metrics
    - Счётчики (Counters)
    - Гистограммы (Histograms)
- Prometheus
- Grafana дашборд

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-23](https://gitlab.golang-school.ru/potok-2/lessons/lesson-23)

ДЗ:

- Рекомендую посмотреть:
    - [https://youtu.be/WQmpeOvCCUY](https://youtu.be/WQmpeOvCCUY)
    - [https://youtu.be/ePZPyIbuG-k](https://youtu.be/ePZPyIbuG-k)
    - [https://youtu.be/8KaHRs93UJw](https://youtu.be/8KaHRs93UJw)
- Можно почитать:
    - Prometheus [https://habr.com/ru/companies/tochka/articles/683608/](https://habr.com/ru/companies/tochka/articles/683608/)
    - Prometheus [https://habr.com/ru/companies/tochka/articles/685636/](https://habr.com/ru/companies/tochka/articles/685636/)

## 24. Логи. Трейсинг. Бенчмарки. Профилирование. Линтеры

Запись: [https://disk.yandex.ru/d/WZ9UXpX6xf_R7A](https://disk.yandex.ru/d/WZ9UXpX6xf_R7A)

Содержание:

- Логи, LogQL, Grafana Loki
- Трейсинг, OpenTelemetry, Span, TraceID, SpanID
- Бенчмарки
- Профилирование с помощью pprof
- Линтеры, golangci-lint
- Файл настроек линтеров .golangci.yml

Материалы:

- [https://gitlab.golang-school.ru/potok-2/lessons/lesson-24](https://gitlab.golang-school.ru/potok-2/lessons/lesson-24)

ДЗ:

- Посмотреть на документацию LogQL: [https://grafana.com/docs/loki/latest/query/](https://grafana.com/docs/loki/latest/query/)
- Посмотреть примеры запросов: [https://grafana.com/docs/loki/latest/query/query_examples/](https://grafana.com/docs/loki/latest/query/query_examples/)
- Посмотреть примеры по инcтрументированию кода OpenTelemetry [https://opentelemetry.io/docs/languages/go/getting-started/](https://opentelemetry.io/docs/languages/go/getting-started/)
- Рекомендую посмотреть, доклад одного из авторов golangci-lint (единственное и до сих пор актуальное видео) [https://youtu.be/VlnxsfSs1ms](https://youtu.be/VlnxsfSs1ms)