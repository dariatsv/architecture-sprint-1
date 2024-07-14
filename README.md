# Задание 1
Запуск проекта: npm install и npm start или через docker-compose.

Address: http://localhost:3000/

Инструмент - Webpack Module Federation

Микрофронтенды:

    1. Auth - сервис авторизации и профиля пользователя

    2. Card - сервис карточки пользователя - добавление, обновление, создания и удаления карточки/мест пользователя

    3. Profile - сервис профиля пользователя - добавление, редактирование, управление профилем пользователя

# Задание 2

Задача: Разбить монолит Платежного сервис на микросервисы.

[Ссылка на решение](arch-sprint-1.drawio)

Микросервисы:
- Апелляционный сервис - отслеживает апелляции пользователей по платежам
- Сервис технической поддержки - отслеживает заявки на тех. поддержку от пользователей
- Сервис услуг - добавление, обновление - редактирование, поиск услуг
- Платежный сервис - интеграционный сервис по работе с транзакциями и взаимодействие с внешними платежными сервисами (Яндекс.Pay и т.п.)
- Сервис нотификаций - рассылка уведомлений пользователям
- Сервис товаров - добавление, обновление - редактирование, поиск товаров
- Сервис заказов - добавление, обновление - редактирование, поиск заказов
- Сервис аукционов - работа с аукционами пользователей
- Сервис отчетности - сбор статистики по работе системы
- Сервис аунтефикации - регистрация, авторизация пользователей, присвоения ролей
- Дополнительно: Мониторинг - Для сбора статистики по работе сервиса необходимо внедрить сбор метрик - Prometheus, для визуализации - Grafana. Также необходимо отслеживать и агрегировать логи - для этого используем ELK.

Микросервисы на backend будут общаться через брокер сообщения - Kafka, Rabbit.

Каждый микросервис имеет свою БД - Postgres. Использован Application Pattern - Database per Service
