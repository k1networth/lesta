# Задание 2: Docker compose

Создайте docker-compose.yaml, который поднимет 2 контейнера:
- Собирает Flask приложение из первой части.
- Redis из образа redis:alpine как кеш.

Необходимо обновить app.py, чтобы он использовал Redis.

При запросе к /count увеличивал счетчик посещений и возвращал его.

Запустите docker-compose и убедитесь, что сервисы работают корректно.

``` sh
docker-compose up --build

curl http://localhost:5000/ping

curl http://localhost:5000/count

# проверка на 1000 запросов

for i in {1..1000}; do
  curl http://localhost:5000/count
done
```
