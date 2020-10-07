# Bookmarks
Приложение, которое дает пользователям возможность делиться фотографиями и картинками, которые они нашли в интернете.

### В проекте реализованы:
- `система аутентификации`, для того чтобы пользователи могли регистрироваться и заходить под своим аккаунтом, редактировать профиль, менять пароль;
- `система подписок`, чтобы пользователи могли наблюдать за обновлениями, происходящими у их друзей;
- отображение количества `просмотров` и `лайков` картинок;
- `лента новостей` пользователей, чтобы каждый мог видеть обновленияу тех, на кого подписался.

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
- Активируйте виртуальное окружение `source venv/bin/activate`
- Установите зависимости `pip install -r requirements.txt`
- Накатите миграции `python manage.py migrate`
- Создайте суперпользователя Django `python manage.py createsuperuser --username admin --email 'admin@example.com'`
- Запустите сервер разработки Django `python manage.py runserver`

### Локальное тестирование
Чтобы протестировать букмарклет, нам необходим `Ngrok`.
- [Скачайте](https://ngrok.com/download) и запустите `Ngrok`, выполнив команду `./ngrok http 8000`
- Сопируйте домен, который вам назначил `Ngrok`:

![ngrok](https://i.imgur.com/RkmvmEK.png)

- Добавьте его в шаблон `/images/templates/bookmarklet_launcher.js`

![bookmarklet_launcher](https://i.imgur.com/1gKIxrC.png)

- В файле `/images/static/js/bookmarklet.js` замените URL на новый адрес с протоколом HTTPS:

![var site_url](https://i.imgur.com/yJK77cS.png)

- Откройте `https://f51819bb1c07.ngrok.io/account/`, заменив ваш домен `Ngrok`.
- Войдите в аккаунт и перетащите кнопку `BOOKMARK IT` в закладки браузера:

![BOOKMARK](https://i.imgur.com/klzRyDf.png)

- Перейдите на любой сайт и кликните на `BOOKMARK IT`. Вы увидите, как справа
появился белый блок, содержащий все `JPEG-картинки` текущего сайта с размером больше, чем `100×100` пикселей

![image](https://i.imgur.com/0Q9WzO3.png)

- Нажмите на любую картинку и откроется форма добавления:

![jpeg](https://i.imgur.com/nwLGp35.png)

- После добавления картинки на сайт, она появляется в вашем личном кабинете

![LK](https://i.imgur.com/IYvVtEs.png)

## В разработке использованы

- [Python](https://www.python.org/)
- [Django](https://www.djangoproject.com/)
- [Pillow](https://pypi.org/project/Pillow/)
- [Sorl-thumbnail](https://pypi.org/project/sorl-thumbnail/)
- [Redis](https://redis.io/)
- [Ngrok](https://ngrok.com/)

## Лицензия
Этот проект лицензируется по лицензии `BSD 3-Clause License` - см. [LICENSE.md](https://github.com/SergePogorelov/bookmarks/blob/master/LICENSE) для получения подробной информации.

_По книге [Антонио Меле: Django 2 в примерах](https://dmkpress.com/catalog/computer/programming/python/978-5-97060-746-6/)_
