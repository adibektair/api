# api
Watch README

## base url: https://chat.rossonero.kz/api/

## Log in:
### `sign-up`
`POST: { login: 'student', password : '123' }`

`RESPONSE: {
    "success": true,
    "user": {
        "id": 2,
        "first_name": "Isma",
        "login": "student",
        "last_name": "Student",
        "role_id": 3,
        "group_id": 1,
        "created_at": null,
        "updated_at": "2019-03-12 18:01:47"
    },
    "token": "ijEZSaaoZo9o0XE1HjrRhQlseAPePf6m0G3"
}`


## Получить список одногруппников:
### `get-groupmates`
`POST: {'token':'your token'}`
`RESPONSE: {
    "state": "success",
    "users": [
        {
            "id": 3,
            "first_name": "Guldana",
            "login": "guldanash",
            "last_name": "Shyntore",
            "role_id": 3,
            "group_id": 1,
            "created_at": null,
            "updated_at": null
        }
    ]
}`



## Получить список Новостей:
### `get-news`
`GET`
`RESPONSE: {
    "news": [
        {
            "id": 1,
            "title": "Title test",
            "text": "Test news",
            "author_id": 1,
            "image_path": "null ",
            "created_at": "2019-03-13 00:00:00",
            "updated_at": "2019-03-14 00:00:00"
        }
    ]
}`


## Получить список чатов:
### `get-chats`
`POST: {token: your token}`
`RESPONSE: {
    "chats": [
        {
            "id": 1,
            "isGroup": 1,
            "group_name": "IS 182 M",
            "group_id": 1,
            "updated_at": "2019-03-13 00:00:00",
            "last_message": "",
            "user_id": null,
            "username": " "
        },
        {
            "id": 2,
            "isGroup": 0,
            "group_name": null,
            "group_id": null,
            "updated_at": "2019-03-13 11:45:28",
            "last_message": "Hi Isma!",
            "user_id": 2,
            "username": "Isma Student"
        }
    ],
    "state": "success"
}`




## Написать сообщение:
### `send-message`
`POST: {
token: your token,
group_id: БЕРЕШЬ ИЗ ЗАПРОСА get-chats если это не групповой чат, не отправляй этот параметр
text: текст сообщения
reciever_id: ID получателя, если это не групповой чат можно взять в запросах getChats или Search
file: FILE
}`
`RESPONSE: {
    "state": "success"
}`




## Вывести сообщения конкретного чата:
### `get-chat-messages`
`POST: {
token: your token,
chat_id: БЕРЕШЬ ИЗ ЗАПРОСА get-chats 
ЕСЛИ ТЫ ИЩЕШЬ ЧЕЛОВЕКА В ПОИСКЕ, СООТВЕТСВЕННО ЧАТА МОЖЕТ И НЕ БЫТЬ С НИМ, ПОЭТОМУ ТЫ ДОЛЖЕН ОТПРАВИТЬ НЕ chat_id, А 
reciever_id - который берешь с поиска
}`

`RESPONSE: {
    "state": "success",
    "messages": [
        {
            "id": 4,
            "author_id": 2,
            "text": "Hello Guldana!",
            "group_id": null,
            "file_path": null,
            "created_at": "2019-03-13 11:44:13",
            "updated_at": "2019-03-13 11:44:13",
            "reciever_id": 3
        },
        {
            "id": 5,
            "author_id": 3,
            "text": "Hi Isma!",
            "group_id": null,
            "file_path": null,
            "created_at": "2019-03-13 11:45:28",
            "updated_at": "2019-03-13 11:45:28",
            "reciever_id": 2
        }
    ]
}`



## Поиск людей:
### `search`
`POST: {
token: your token,
field: текст поиска
}`

`RESPONSE: {
    "users": [
        {
            "id": 3,
            "first_name": "Guldana",
            "login": "guldanash",
            "last_name": "Shyntore",
            "role_id": 3,
            "group_id": 1,
            "created_at": null,
            "updated_at": null,
            "department_id": null
        }
    ],
    "state": "success"
}`



## Загрузка аватарки:
### `update-avatar`
`POST: {
token: your token,
avatar: formdata image
}`

`RESPONSE: {
    "image_path" : ""
    "state": "success"
}`

## Set push id:
### `set-pushid`
`POST: {
token: your token,
push_id: string
}`

`RESPONSE: {
    "state": "success"
}`



## Изменить пароль:
### `change-password`
`POST: {
token: your token,
password: текущий пароль
new_password: новый пароль
}`

`RESPONSE: {
    "state": "success"
}`

## Set push id:
### `set-pushid`
`POST: {
token: your token,
push_id: string
}`

`RESPONSE: {
    "state": "success"
}`
