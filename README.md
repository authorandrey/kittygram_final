# Kittygram

Kittygram - социальная сеть для котиков. Можно добавлять фотографии котиков, оставлять описания, просматривать котиков других пользователей, редактировать и удалять записи.

## Стек
- Backend: Python, Django, DRF, PostgreSQL, Gunicorn
- Frontend: React
- Другое: Docker, Nginx, GitHub Actions, Docker Hub

## Запуск локально
1. Клонируйте репозиторий:
   ```bash
   git clone https://github.com/authorandrey/kittygram_final.git
   cd kittygram_final
   ```
2. Создайте файл .env на основе .env.example (поставьте свой секретный ключ для Django)
3. Запустите контейнеры:
   ```bash
   docker compose up --build
   ```
4. Выполните миграции и сбор статики:
   ```bash
   docker compose exec backend python manage.py migrate
   docker compose exec backend python manage.py collectstatic --no-input
   docker compose exec backend cp -r /app/collected_static/. /backend_static/static/
   ```
5. Откройте `http://localhost:9000`