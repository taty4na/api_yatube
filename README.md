# API Yatube

API сервис для социальной сети Yatube.

Сервис можно использовать для программного доступа к данным и работы с социальной сетью.
У всех пользователей сервиса есть доступ для просмотра постов. Для подписки на понравившегося автора, или добавления своего поста необходимо зарегистрироваться.
Данные предоставлены в формате JSON, которые можно программно собирать, измерять и анализировать.

## Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone git@github.com:taty4na/api_yatube.git
```
```
cd api_yatube
```

Cоздать и активировать виртуальное окружение:
```
python3 -m venv venv
```
```
source venv/bin/activate
```

Установить зависимости из файла requirements.txt:
```
python3 -m pip install --upgrade pip
```
```
pip install -r requirements.txt
```

Выполнить миграции:
```
python3 manage.py migrate
```

Запустить проект:
```
python3 manage.py runserver
```

## Документация и примеры запросов:

Документация для API Yatube доступна по адресу http://127.0.0.1:8000/redoc/. 
В документации описано, как работает API и представлены примеры запросов ко всем эндпоинтам.

Некоторые примеры запросов:

#### Получить список всех публикаций.
```
GET http://127.0.0.1:8000/api/v1/posts/
```

***Пример ответа***
```
{
  "count": 123,
  "next": "http://api.example.org/accounts/?offset=400&limit=100",
  "previous": "http://api.example.org/accounts/?offset=200&limit=100",
  "results": [
    {
      "id": 0,
      "author": "string",
      "text": "string",
      "pub_date": "2021-10-14T20:41:29.648Z",
      "image": "string",
      "group": 0
    }
  ]
}
```

#### Добавление новой публикации в коллекцию публикаций.
```
POST http://127.0.0.1:8000/api/v1/posts/
{
  "text": "string",
  "image": "string",
  "group": 0
}
```

***Пример ответа***
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

#### Добавление нового комментария к публикации.
```
POST http://127.0.0.1:8000/api/v1/posts/{post_id}/comments/
{
  "text": "string"
}
```

***Пример ответа***
```
{
  "id": 0,
  "author": "string",
  "text": "string",
  "created": "2019-08-24T14:15:22Z",
  "post": 0
}
```



## ***Автор Татьяна***
