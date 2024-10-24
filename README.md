# Telegram Bot с использованием aiogram и интеграцией с бэкендом
Данный проект реализует Telegram-бота на основе фреймворка aiogram. Бот взаимодействует с бэкендом, IP-адрес и порт которого могут задаваться через переменные окружения.

## Быстрый старт
### Шаг 1: Создание файла .env
В корневой директории проекта создайте файл .env, который будет содержать токен вашего бота и информацию для подключения к бэкенду.

Пример файла .env:
``` env
API_TOKEN=ваш-токен-бота
BACKEND_IP=127.0.0.1  # или IP-адрес вашего бэкенда
BACKEND_PORT=8000     # порт, на котором работает бэкенд
```

- API_TOKEN: Токен вашего Telegram-бота, который можно получить у [BotFather](https://telegram.me/BotFather). 
- BACKEND_IP: IP-адрес сервера бэкенда, с которым бот будет взаимодействовать. 
- BACKEND_PORT: Порт, на котором работает ваш бэкенд.

### Шаг 2: Сборка Docker-образа
После того как вы настроили файл .env, соберите Docker-образ, выполнив следующую команду в директории проекта:

``` bash
docker build -t telegram-bot .
```
Эта команда создаст Docker-образ с именем telegram-bot на основе предоставленного Dockerfile.

### Шаг 3: Запуск Docker-контейнера
После сборки образа вы можете запустить контейнер с помощью следующей команды, чтобы он использовал переменные окружения из файла .env:
```
docker run --env-file .env telegram-bot
```
Эта команда запустит контейнер и загрузит переменные окружения из файла .env.