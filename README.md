# Bookmarks
Приложение, которое дает пользователям возможность делиться фотографиями и картинками, которые они нашли в интернете.

### В проекте реализованы:
- система аутентификации, для того чтобы пользователи могли регистрироваться в соцсети, заходить под своим аккаунтом, редактировать профиль и менять пароль;
- система подписок, чтобы пользователи могли наблюдать за обновлениями, происходящими у их друзей;
- отображение картинок, которыми делятся пользователи;
- лента новостей пользователей, чтобы каждый мог видеть обновленияу тех, на кого подписался.

## Установка
Эти инструкции помогут вам создать копию проекта и запустить ее на локальном компьютере для целей разработки и тестирования.

**Перед тем, как начать:**
1. Если вы не пользуетесь `Python 3`, вам нужно будет установить инструмент `virtualenv` при помощи `pip install virtualenv`. 
Если вы используете `Python 3`, у вас уже должен быть модуль [venv](https://docs.python.org/3/library/venv.html), установленный в стандартной библиотеке.

2. Установите `Redis`. Воспользуйтесь [инструкциями с официального сайта](https://redis.io/download) или командами:
```
wget http://download.redis.io/releases/redis-stable.tar.gz
tar xzf redis-stable.tar.gz
cd redis-stable && make
```
Запустите сервер `Redis` командой `src/redis-server` из папки `redis-stable`

### Запуск проекта (на примере Linux)
- Создайте на своем компютере папку проекта `mkdir bookmarks` и перейдите в нее `cd bookmarks`
- Склонируйте этот репозиторий в текущую папку `git clone https://github.com/SergePogorelov/bookmarks.git .`
- Создайте виртуальное окружение `python3 -m venv venv`
- Установите зависимости `pip install -r requirements.txt`
- Накатите миграции `python manage.py migrate`
- Создайте суперпользователя Django `python manage.py createsuperuser --username admin --email 'admin@example.com'`
- Запустите сервер разработки Django `python manage.py runserver`

## В разработке использованы

- [Python](https://www.python.org/)
- [Django](https://www.djangoproject.com/)
- [Pillow](https://pypi.org/project/Pillow/)
- [Sorl-thumbnail](https://pypi.org/project/sorl-thumbnail/)
- [Redis](https://redis.io/)

_По книге [Антонио Меле: Django 2 в примерах](https://dmkpress.com/catalog/computer/programming/python/978-5-97060-746-6/)_
