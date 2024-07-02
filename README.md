##﻿# shorten-url-fiber-redis

# Данный сервис позволят сокращать объемные ссылки до 6 символов.

# Установлено ограничение до 10 ссылок в 30 минут. При превышении данного лимита, вызывается ошибка: "Rate limit exceeded".

# Сервис позволяет использоваьть сокращенные ссылки в течение 24 часов.

Пример POST запроса и ответа сериса по адресу: localhost:3000/api/v1

## запрос:
{"url":"https://www.youtube.com/watch?v=OnVoIAAJeOk"}

# ответ:
{
    "URL": "https://www.youtube.com/watch?v=OnVoIAAJeOk",
    "short": "localhost:3000/194d12",
    "Expiry": 24,
    "rate_remaining": 9,
    "XRateLimitReset": 30
}

![Uploading image.png…]()

#                       ...

![Uploading image.png…]()



## Пример POST запроса и ответа сериса при истичении лимита по адресу: localhost:3000/api/v1

# запрос:
{"url":"https://www.youtube.com/watch?v=qwwq"}

# ответ:
{
    "error": "Rate limit exceeded",
    "rate_limit_rest": 25
}

![Uploading image.png…]()




