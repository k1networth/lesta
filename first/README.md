# Задание 1: Docker image
Создайте Dockerfile, который:
- Используется python3.9 как базовый образ.
- Копирует локальный файл app.py в контейнер.
- Устанавливает зависимости из requirements.txt.
- Запускает Flask-приложение при старте контейнера.

Необходимо создать app.py - простое Flask api с 1 эндпоинтом /ping, который возвращает {"status":
"ok"}.

Контейнер должен запуститься на порту 5000. Проверка работы контейнера производится путем
отправки curl запроса http://localhost:5000/ping

``` sh
docker build -t flask-app .

docker run -d -p 5000:5000 flask-app

curl http://localhost:5000/ping
```
