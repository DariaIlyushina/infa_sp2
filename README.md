## YaMDb
Проект является агрегатором отзывов о фильмах, книгах и музыке
Авторы: Илюшина Дарья, Шурховецкий, Скрипкин Максим

## Установка

Клонируйте репозиторий с GitHub:
```
git clone https://github.com/DariaIlyushina/api_yamdb/
```

Перейдите в корневую директорию проекта, создайте и активируйте виртуальное окружение: 
```
$ python -m venv venv
...
$ source venv/Scripts/activate
```

Установите зависимости:
```
$ pip install requirements.txt
```

Запустите сервер разработчика:
```
$ python manage.py runserver
```
## Несколько примеров использования API
**GET /titles/** - получить список всех произведений  
Ответ (200):  
|Ключ|Значение|Описание|
|----|--------|--------|
|"id"|number|ID произведения|
|"name"|"string"|Название|
|"year"|number|Год выпуска|
|"rating"|number|Рейтинг произведения|
|"description"|"string"|Описание|
|"genre"|Array of objects|Жанр|
||"name"|Название жанра|
||"slug"|Поле "slug" |
|"category"|objects|Категория|
||"name"|Название категории объекта|
||"slug"|Поле "slug" |
  
**POST /auth/email/** - передача confirmation_code на адрес эл.почты  
Запрос:  
| Ключ |Значение|Описание|
| :--- |:------:|-------:|
| email|"string"|адрес эл.почты|

В результате, пользователь получает на указанный адрес эл.почты код подтверждения __confirmation_code__  

**PATCH /users/me/** - изменить данные своей учетной записи  
Запрос:  
| Ключ |Значение|Описание|
| :--- |:------:|-------:|
|"first_name"|"string"|Имя|
|"last_name"|"string"|Фамилия|
|"username"|"string"|Username|
|"bio"|"string"|О себе|
|"email"|"string"|Адрес электронной почты|
|"role"|"string"| Enum: "user" "moderator" "admin"|  

Ответ (200):
|Ключ|Значение|Описание|
|----|--------|--------|
|"first_name"|"string"|Имя|
|"last_name"|"string"|Фамилия|
|"username"|"string"|Username|
|"bio"|"string"|О себе|
|"email"|"string"|Адрес электронной почты|
|"role"|"string"| Enum: "user" "moderator" "admin"|  

** 

__**Полная информация о данном API находится по адресу http://127.0.0.1:8000/redoc/**__