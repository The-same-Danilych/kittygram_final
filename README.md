# Kittygram — социальная сеть для котиков 🐱

    Проект Kittygram — это веб-приложение, где пользователи могут создавать профили своих котиков, загружать их фотографии, отмечать достижения и просматривать карточки других котиков. Приложение построено на микросервисной архитектуре и полностью запускается в Docker-контейнерах.

## Возможности

    - Регистрация и аутентификация пользователей (JWT-токены).
    - Создание, редактирование и удаление карточек котиков.
    - Загрузка изображений котиков.
    - Просмотр ленты с карточками котиков других пользователей.
    - Присвоение достижений котикам.
    - Админка Django для управления контентом.

## Технологический стек

### Backend
    - **Django 3.2.3** — веб-фреймворк.
    - **Django REST Framework 3.12.4** — создание REST API.
    - **Djoser 2.1.0** — аутентификация и управление пользователями.
    - **PostgreSQL 13** — реляционная база данных.
    - **Gunicorn 20.1.0** — WSGI-сервер для продакшена.
    - **Psycopg2-binary** — адаптер для работы с PostgreSQL.

### Frontend
    - **React 18** (сборка через Create React App).
    - **Node.js 18** — среда выполнения.
    - **npm** — менеджер пакетов.

### Инфраструктура
    - **Docker** и **Docker Compose** — контейнеризация и оркестрация.
    - **Nginx 1.22.1** — веб-сервер и reverse-proxy (gateway).
    - **GitHub Actions** — CI/CD (автоматическое тестирование и деплой на Docker Hub).

### Дополнительно
    - **Ruff** — линтер для Python.
    - **pytest** — тестирование backend.

## Как развернуть проект локально

### 1. Клонировать репозиторий
    ```bash
    git clone https://github.com/The-same-Danilych/kittygram_final.git
    cd kittygram_final

### 2. Создать .env файл
 В корне проекта создай файл .env со следующими переменными (пример — в .env.example):

    env
    POSTGRES_DB=kittygram
    POSTGRES_USER=kittygram_user
    POSTGRES_PASSWORD=kittygram_password
    DB_HOST=db
    DB_PORT=5432
    SECRET_KEY=секретный-ключ-django
    ALLOWED_HOSTS=localhost,127.0.0.1
    DEBUG=False
### 3. Запустить контейнеры
    bash
    docker compose up --build
    После сборки приложение будет доступно по адресу: http://localhost:8000

### 4. Применить миграции
    bash
    docker compose exec backend python manage.py migrate
