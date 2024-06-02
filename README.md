<p align="center">
     <img src="./RZD Russian Railways Logo Vector.png" alt="Логотип проекта" width="500" style="display: inline-block; vertical-align: middle; margin-right: 10px;"/>  <br/>
     <H2 align="center">Команда Ikanam 1218 </H2> 
    <H2 align="center">Автоматизация выявления технологических нарушений"</H2> 
</p>


Репозиторий команды ikanam 1218
"Веб-сервис для видеодетекции технологических нарушений"
- Ссылка на прототип - http://89.232.160.30:7484/


Описание проекта
Этот репозиторий содержит исходный код и ресурсы для веб-сервиса, который анализирует видеозаписи с нагрудных регистраторов для определения правильности использования СИЗ, наличия спецодежды и выявления технологических нарушений.

Архитектура решения
Технологии
- Нейронные сети: Pytorch, YoloV8, TorchVision, Scikit-learn
- Визуализация аналитики: Plotly
- Веб-приложение: Streamlit
- Брокер сообщений: RabbitMQ
- Хранение данных: MongoDb 

Структура репозитория
- worker/: Код микросервиса для распознавания архивов и rtc трансляций, внути него есть yolo модель
- notif/: Код микросервиса для рассылки уведомлений о детектах
- lct/: Код микросервиса для выставления задач распознавания и просмотрв результатов

Использование
+ 1 вариант, без docker 
  - Клонируйте репозиторий: git clone https://github.com/yourusername/illegal-trade-detection.git
  - Установите зависимости в каждом микросервисе: poetry install  
  - Установить переменные окружения для rabbitMq и mongoDb
  - Запустить каждый микросервис: poetry run start
+ 2 вариант, в docker
  - Клонируйте репозиторий: git clone https://github.com/yourusername/illegal-trade-detection.git
  - запустить все миикросервисы из docker-compose: docker-compose up
    
*Список всех переменных окружения:
MONGO_HOST: Адрес сервера MongoDB.
MONGO_PORT: Порт сервера MongoDB (по умолчанию 27017).
MONGO_DATABASE: Имя базы данных MongoDB.
MONGO_USERNAME: Имя пользователя MongoDB для аутентификации.
MONGO_PASSWORD: Пароль пользователя MongoDB для аутентификации.
NOTIF_PORT: Порт для сервиса уведомлений.
ADMIN_NOTIF_PSWD: Пароль для создания уведомлений.
NOTIF_PSWD: Пароль для получения уведомлений.
NOTIF_URL: URL сервиса уведомлений.
RABBITMQ_HOST: Адрес сервера RabbitMQ.
RABBITMQ_PORT: Порт сервера RabbitMQ (по умолчанию 5672).
RABBITMQ_USER: Имя пользователя RabbitMQ для аутентификации.
RABBITMQ_PASSWORD: Пароль пользователя RabbitMQ для аутентификации.
RABBITMQ_VHOST: Виртуальный хост RabbitMQ.
EXCHANGE_NAME: Имя обмена RabbitMQ для входных видео.
DEQUE_NAME: Имя очереди RabbitMQ для входных видео.
BINDING_KEY: Ключ привязки RabbitMQ (используется при маршрутизации сообщений).
MODEL_PATH: Путь к файлу yolo модели.
USER_LOGIN: Логин для авторизации на сервисе
USER_PASSWORD: Пароль для авторизации на сервисе
*Дефотные данные для входа:
- Логин: jsmith
- Пароль: abc
