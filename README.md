# HTTP Server for providing JWT tokens (Go)

[![Go](https://img.shields.io/badge/Go-1.21+-blue.svg)](https://golang.org/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15+-blue.svg)](https://www.postgresql.org/)
[![Docker](https://img.shields.io/badge/Docker-24.0+-blue.svg)](https://www.docker.com/)

Простой HTTP-сервер на Go для генерации, хранения и проверки JWT-токенов.

## 🚀 Функционал
- **JWT-авторизация** (Middleware для некоторых эндпоинтов)
- **API Endpoints**:
  - `GET /refresh` - обновление токенов
  - `GET /getguid` - предоставление guid пользователя
  - `GET /logout` - разлогинить пользователя
  - `GET /provide/{id}` - предоставление токенов
  - `POST /registrate` - регистрация пользователя
- **Хранилище**: PostgreSQL с миграциями (`goose`)
- **Docker-сборка**: Готовый `docker-compose.yml` для развертывания

## 📦 Установка
### Предварительные требования
- Go 1.21+
- PostgreSQL 15+
- Docker 24.0+

### Запуск локально
1. Клонируйте репозиторий:
   ```bash
   git clone https://github.com/Dobi-Vanish/MedodsTask
2. Перейдите в папку deployments и запустите проект:
   ```bash
   cd auth-service/deployments
   docker-compose -f docker-compose.yml up -d
### Пример успешного запроса
 Запуск коллекции в Postman для проверки:  
 
![Без имени](https://github.com/user-attachments/assets/1a800bf0-dcd1-4705-8c61-b3e13dd54eed)


 ### Примечание
 В пункте про получение пары токенов было сказано "...для пользователя с идентификатором (GUID) указанным в параметре запроса;", но не совсем понятно - имеется в виду в теле запроса или значение должно передаваться через URL. В данном случае для получения токенов необходимо будет указывать GUID пользователя в URL'e. Для этого необходимо зарегестрировать нового пользователя через готовую конечную точку и использовать сгенерированный GUID из базы данных.  
 Если есть какие-либо другие замечания - прошу указать, если надо как-либо исправить.

