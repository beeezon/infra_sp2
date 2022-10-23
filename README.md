### Описание проекта:

Проект разработан для демонстрации возможностей технологии Docker.
Данная технологи позволяет развернуть и запустить проект без проблем, связанных с настройкой операционной системы, версией интерпритатора, конфликтов библиотек и т.д.

### Как запустить проект:

Для запуска проекта необходимо склонировать репозиторий с облачного сервера Docker, используя команду:

```
docker pull kirillovboris92/infra-web:tagname
```
Выболнить сборку контейнеров, используя команду:
```
docker-compose up -d --build 
```
Выполнить по очереди команды, для запуска миграций и создания суперпользователя:
```
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
docker-compose exec web python manage.py collectstatic --no-input 
```

### Пример наполнения файла .env:

- DB_ENGINE=django.db.backends.postgresql # указываем, что работаем с postgresql
- DB_NAME=postgres # имя базы данных
- POSTGRES_USER=postgres # логин для подключения к базе данных
- POSTGRES_PASSWORD=postgres # пароль для подключения к БД (установите свой)
- DB_HOST=db # название сервиса (контейнера)
- DB_PORT=5432 # порт для подключения к БД 



### Автор (Telegram - Git):
@Boris Kirillov (teamlead) - beeezon