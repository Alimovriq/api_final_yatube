# Проект «API для Yatube»

[![Python](https://img.shields.io/badge/-Python-464646?style=flat-square&logo=Python)](https://www.python.org/)
[![DjangoREST](https://img.shields.io/badge/DJANGO-REST-ff1709?style=for-the-badge&logo=django&logoColor=white&color=ff1709&labelColor=gray)](https://www.django-rest-framework.org/)
[![sqlite](https://skillicons.dev/icons?i=sqlite)](https://sqlite.org/)

## Описание
Данный API предоставляет возможность пользоваться функционалом блога не посещая сайт.

## Возможности
- Создание / Просмотр / Редактирование / Удаление постов
- Создание / Просмотр / Редактирование / Удаление комментариев
- Подписка на пользователей
- Поиск по подпискам
- Просмотр сообществ

Документация доступна по адресу: ```http://127.0.0.1:8000/redoc```

## Технологии
 - Python 3.7.13
 - Django 2.2.16
 - REST Framework 3.12.4
 - PyJWT 2.1.0
 - подробнее см. прилагаемый файл зависимостей requrements.txt

### Установка
Клонировать репозиторий и перейти в него в командной строке:

```
git clone git@github.com:Alimovriq/api_final_yatube.git
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
```

```
source env/bin/activate
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
python3 manage.py makemigrations
```
```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```

### Примеры
Для формирования запросов использовалась программа Postman, доступная по адресу: ```https://www.postman.com/```

##### 1. Получние токена
Отправляем POST запрос на эндпоинт api/v1/jwt/create/ с заполненными полями в Body:
- username - имя пользователя (обязательное поле)
- password - пароль пользователя (обязательное поле)

![Иллюстрация к получению токена](https://github.com/Alimovriq/api_final_yatube/blob/master/yatube_api/static/2.png)


Важно:
Токен "access" требуется для аутентификации пользователя. Срок действия = 1 день.
Токен "refresh" требуется для обновления токена "access"

##### 2. Создаем новый пост
Отправляем POST запрос на эндпоинт api/v1/posts/ с заполненными полями в Body:
- text - текст публикации (обязательное поле)
- image - изображение публикации (необязательное поле)
- group - сообщество, к которой относится публикация (необязательное поле)

![Иллюстрация к созданию поста №1](https://github.com/Alimovriq/api_final_yatube/blob/master/yatube_api/static/3.png)

![Иллюстрация к созданию поста №2](https://github.com/Alimovriq/api_final_yatube/blob/master/yatube_api/static/4.png)

### Автор
Алимов Ринат
https://github.com/Alimovriq
