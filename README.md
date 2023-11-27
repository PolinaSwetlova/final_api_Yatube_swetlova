# Описание

Проект представляет собой API для проекта yatube.

Для аутентификации использованы JWT-токены.

У неаутентифицированных пользователей доступ к API только на чтение.

Аутентифицированным пользователям разрешено изменение и удаление своего контента; в остальных случаях доступ предоставляется только для чтения.

# Установка

Клонировать репозиторий и перейти в него в командной строке:

git clone git@github.com:PolinaSwetlova/api_final_yatube.git

cd api_final_yatube

Cоздать и активировать виртуальное окружение:

python -m venv venv

source venv/Scripts/activate

Установить зависимости из файла requirements.txt:

python -m pip install --upgrade pip

pip install -r requirements.txt

Выполнить миграции:

python manage.py migrate

Запустить проект:

python manage.py runserver

# Примеры

Для доступа к API необходимо получить токен: 
Нужно выполнить POST-запрос localhost:8000/api/v1/token/ передав поля username и password. API вернет JWT-токен

Дальше, передав токен можно будет обращаться к методам, например: 

/api/v1/posts/ (GET, POST, PUT, PATCH, DELETE)

При отправке запроса передавайте токен в заголовке Authorization: Bearer <токен>
