# StatisticsAPI

Сервис для аналитики и отчетности о текущем положении дел над переводами с возможностью внедрения своих метрик. Отсюда можно вытянуть данные 
* о рейтинге переводчиков
* о количестве переводов
* о проценте завершенности
* о динамике переводов того или иного направления.

Установка
---------

Dev env

Prerequsisites - [docker](https://docs.docker.com/engine/understanding-docker/) && [docker compose](https://docs.docker.com/compose/overview/)

```bash
$ git clone git@github.com:kursomir/StatisticsAPI.git
$ cd StatisticsApi
$ docker-compose build
$ docker-compose up -d
$ cp .env.example .env
```

Example config for docker env

```
#.env
APP_ENV=local
APP_DEBUG=true
APP_KEY=SomeRandomKey!!!

DB_CONNECTION=pgsql
DB_HOST=core_db
DB_PORT=5432
DB_DATABASE=core_api
DB_USERNAME=kursomir
DB_PASSWORD=kursomir

ES_HOST=elasticsearch
ES_PORT=9200
```

Populate db with fixtures from core api:

```bash
$ docker-compose run coreapi php artisan db:seed
```