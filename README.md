![](https://img.shields.io/badge/Python-3.7.5-blue) 
![](https://img.shields.io/badge/Django-2.2.16-green)
![](https://img.shields.io/badge/DjangoRestFramework-3.12.4-red)
![](https://img.shields.io/badge/Docker-3.8-yellow)
<br><br>
## Название проекта
**«YaMDb API»** - проект YaMDb собирает отзывы пользователей на различные произведения.

**Возможности:**<br>
:black_small_square: Регистрация на сайте, получение токена, изменение данных своей учетной записи<br>
:black_small_square: Раздаление прав пользователей согласно, назначенной ему роли<br>
:black_small_square: Возможность, согласно авторизации выполнять следующие дествия: получать, добавлять и удалять - категорию, жанр, произведение, отзыв и комментарий<br>
:black_small_square: Администрирование пользователями<br><br>

## :computer: Технологии в проекте
:small_blue_diamond: Python <br>
:small_blue_diamond: Django <br>
:small_blue_diamond: Django REST Framework <br>
:small_blue_diamond: Docker <br>

## :pencil2: Инструкции по запуску (через GitHub)
1. Склонировать репозиторий через консоль:
```sh
git clone https://github.com/Amaterasq/infra_sp2.git
```
2. Создать .env файл внутри директории infra (на одном уровне с docker-compose.yaml)
Пример .env файла:
```sh
SECRET_KEY = 'p&l%385148kslhtyn^##a1)ilz@4zqj=rq&agdol^##zgl9(vs'
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=123
DB_HOST=db
DB_PORT=5432
```
3. Запуск тестов (опционально, если не нужно - переходите к следующему шагу)
Создать и активировать виртуальное пространство, установить зависимости.
Для Windows:
```sh
cd infra_sp2
python -m venv venv
source venv/Scripts/activate
cd api_yamdb
pip install -r requirements.txt
cd ..
pytest
```
Для Mac/Linux:
```sh
cd infra_sp2
python3 -m venv venv
source venv/bin/activate
cd api_yamdb
pip install -r requirements.txt
cd ..
pytest
```
4. Запуск Docker контейнеров:
Убедиться, что Docker установлен и готов к работе
```sh
docker --version
```
Запустите docker-compose
```sh
cd infra/
docker-compose up -d
```
5. Выполните миграции, создайте суперпользователя и перенесите статику:
```sh
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
docker-compose exec web python manage.py collectstatic --no-input
```
6. Наполните базу данных тестовыми данными:
```sh
docker-compose exec web python manage.py dbfill
```
7. Проверьте доступность сервиса
```sh
http://localhost/admin
```

## :bust_in_silhouette: Авторы проекта 

### :small_orange_diamond: Влад Перепечко _(Vlad Vi. Perepechko)_
```html
e-mail: perepechcko.vlad@ya.ru
```
```html
https://github.com/Amaterasq
```