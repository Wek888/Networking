# Кратко

## 1

HTTP — HyperText Transfer Protocol, протокол обмена данными между клиентом и сервером

HTTPS — тот же HTTP, но поверх TLS/SSL шифрование.

Клиент-сервер — клиент (браузер/приложение) шлёт запрос, сервер обрабатывает и отвечает. Один сервер — много клиентов.

Идемпотентность — повторный запрос даёт тот же эффект, что и один. GET, PUT, DELETE — да; POST — нет.

## 2.1. Запрос

1. Метод — `POST`
2. Путь — `/api/users`
3. Версия — `HTTP/1.1`
4. `Content-Type` — тело в JSON
5. `Authorization` — токен доступа (Bearer/JWT), клиент авторизован
6. Тело — после пустой строки: `{"name": "Иван", "email": "ivan@mail.com"}`

## Ответ

1. `201 Created` — ресурс создан
2. `Location` — URL нового ресурса (`/api/users/42`)
3. Тело — созданный пользователь с id=42

## 2.3. Запросы

Список товаров
```http
GET /api/products HTTP/1.1
Host: example.com
```

Создать товар
```http
POST /api/products HTTP/1.1
Host: example.com
Content-Type: application/json

{"name": "Ноутбук", "price": 50000}
```

Удалить id=7
```http
DELETE /api/products/7 HTTP/1.1
Host: example.com
```

Обновить id=3 (цена 45000)
```http
PUT /api/products/3 HTTP/1.1
Host: example.com
Content-Type: application/json

{"name": "Ноутбук", "price": 45000}
```
