# Берем Python версии 3.9
FROM python:3.9-slim

# Создаем папку /app в контейнере
WORKDIR /app

# Устанавливаем Gunicorn (сервер для запуска Django)
RUN pip install gunicorn==20.1.0

# Копируем файл с зависимостями
COPY requirements.txt .

# Устанавливаем все нужные библиотеки
RUN pip install -r requirements.txt --no-cache-dir

# Копируем весь код бэкенда в контейнер
COPY . .

# Команда для запуска приложения
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "kittygram_backend.wsgi"]