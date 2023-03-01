
## Инструкция для запуска приложения в контейнерах
Клонируем репозиторий через командную строку, заходим в директорию с `docker-compose.yaml`
```

git clone https://github.com/Melkumyan777/infra_sp2

cd infra_sp2/infra/
```
Запускаем контейнеры, выполняем миграции, проводим сбор статики
```
docker-compose up -d --build

docker-compose exec web python manage.py migrate

docker-compose exec web python manage.py collectstatic --no-input

```
Для остановки контейнеров :
```

docker-compose down -v

```
## Шаблон наполнения ENV-файла
```
DB_ENGINE=django.db.backends.postgresql

DB_NAME=postgres

POSTGRES_USER=postgres

POSTGRES_PASSWORD=postgres

DB_HOST=db

DB_PORT=5432


```
