### Описание:

Проект «API для Yatube».
Данный проект выполнен с целью познать библиотеку Django REST Framework, с помощью которой можно просто и быстро разрабатывать REST API.

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```bash
git clone https://github.com/evgenlit/api_final_yatube.git
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```bash
python3 -m venv env
source env/bin/activate
python3 -m pip install --upgrade pip
```

Установить зависимости из файла requirements.txt:

```bash
pip install -r requirements.txt
```

Выполнить миграции:

```bash
python3 manage.py migrate
```

Запустить проект:

```bash
python3 manage.py runserver
```

### Примеры запросов

Пример POST-запроса с токеном Антона Чехова: добавление нового поста.
POST .../api/v1/posts/
```bash
{
    "text": "Вечером собрались в редакции «Русской мысли», чтобы поговорить о народном театре. Проект Шехтеля всем нравится.",
    "group": 1
}
```

Пример ответа:
```bash
{
    "id": 14,
    "text": "Вечером собрались в редакции «Русской мысли», чтобы поговорить о народном театре. Проект Шехтеля всем нравится.",
    "author": "anton",
    "image": null,
    "group": 1,
    "pub_date": "2021-06-01T08:47:11.084589Z"
}
```

Пример POST-запроса с токеном Антона Чехова: отправляем новый комментарий к посту с id=14.
POST .../api/v1/posts/14/comments/
```bash
{
    "text": "тест тест"
}
```

Пример ответа:
```bash
{
    "id": 4,
    "author": "anton",
    "post": 14,
    "text": "тест тест",
    "created": "2021-06-01T10:14:51.388932Z"
}
```

Пример GET-запроса с токеном Антона Чехова: получаем информацию о группе.
GET .../api/v1/groups/2/

Пример ответа:
```bash
{
    "id": 2,
    "title": "Математика",
    "slug": "math",
    "description": "Посты на тему математики"
}
```
