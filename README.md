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
