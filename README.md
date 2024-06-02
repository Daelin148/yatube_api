# YATUBE_API

### Что может этот проект
- Аутентифицированные пользователи могут создавать посты и добавлять к ним комментарии
- Анонимные пользователи могут только просматривать контент
- Аутентифицированные пользователи могут подписываться на других пользователей
- Аутентификация доступна по JWT-токену

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/Daelin148/api_final_yatube.git
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python -m venv venv
```

```
source venv/Scripts/activate
```

Установить зависимости из файла requirements.txt:

```
python -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python manage.py migrate
```

Запустить проект:

```
python manage.py runserver
```

### Примеры запросов:

POST /api/v1/posts/
 ```
{
    "text": "string",
    "image": "string",
    "group": 0
}
 ```

 Ответ:
```
{
    "id": 0,
    "author": "string",
    "text": "string",
    "pub_date": "2019-08-24T14:15:22Z",
    "image": "string",
    "group": 0
}
```

GET /api/v1/posts/{id}/

Ответ:
```
{
    "id": 0,
    "author": "string",
    "text": "string",
    "pub_date": "2019-08-24T14:15:22Z",
    "image": "string",
    "group": 0
}
```

GET /api/v1/posts/{post_id}/comments/

Ответ:
```
[
    {
        "id": 0,
        "author": "string",
        "text": "string",
        "created": "2019-08-24T14:15:22Z",
        "post": 0
    }
]
```

GET /api/v1/groups/

Ответ:
```
[
    {
        "id": 0,
        "title": "string",
        "slug": "^-$",
        "description": "string"
    }
]
```

GET /api/v1/follow/

Ответ:
```
[
    {
        "user": "string",
        "following": "string"
    }
]
```


POST /api/v1/jwt/create/
```
{
    "username": "string",
    "password": "string"
}
```

Ответ:
```
{
    "refresh": "string",
    "access": "string"
}
```
