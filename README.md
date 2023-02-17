# Foodgram

Ознакомительная версия проекта доступна по ссылке  https://nooneliveshere.site/

Foodgram - проект, выполненный в рамках обучения в Яндекс Практикуме. Проект позволяет:

- Просматривать рецепты
- Добавлять рецепты в избранное
- Публикование рецепты
- Удалять собственные рецепты или редактировать их
- Скачивать список покупок

## Установка и запуск в docker-compose

Создайте и заполните .env файл в дериктории infra своими данными:
```
# указываем, с какой БД работаем
DB_ENGINE=django.db.backends.postgresql
# имя базы данных
DB_NAME=
# логин для подключения к базе данных
POSTGRES_USER=
# пароль для подключения к БД (установите свой)
POSTGRES_PASSWORD=
# название сервиса (контейнера)
DB_HOST=
# порт для подключения к БД
DB_PORT=
# секретный код приложения
SECRET_KEY=
```

Клонировать репозиторий и перейти в директорию infra:

```
git clone https://github.com/nooneliveshere/foodgram-project-react.git
```

```
cd foodgram-project-react/infra
```
Запустить команду сборки контейнера:

```
docker-compose -d --build
```

Выполнить внутри контейнера миграции, собрать статику:
```
docker-compose exeс backend python3 manage.py makemigrations
docker-compose exeс backend python3 manage.py migrate
docker-compose exec backend python3 manage.py collectstatic --no-input
```

Проект должен быть доступен по http://127.0.0.1, документацию к проекту 
можно будет найти по адресу http://127.0.0.1/api/docs/ 

Учетные данные админа для проверки:
```
master
master@nooneliveshere.site
Cegthgfhjkm1
```