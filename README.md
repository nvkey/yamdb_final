## Проект YaMDb API:

Проект API YaMDb реализует API для сбора отзывов пользователей на произведения.

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone git@github.com:nvkey/infra_sp2.git
```

```
cd infra_sp2/infra
```

Запуск docker-compose:

```
docker-compose up -d --build 
```

Выполнить миграции:

```
docker-compose exec web python manage.py migrate
```

Заполнить базу данных и статику:

```
docker-compose exec web python manage.py usecsv
docker-compose exec web python manage.py collectstatic --no-input 
```

По адресу http://127.0.0.1/redoc/ будет доступна документация для YaMDb API. В документации описано, как должен работать ваш API. Документация представлена в формате Redoc.

Остановка docker-compose:

```
docker-compose down -v 
```
### Авторы
- [p17m0](https://github.com/p17m0) — управление пользователями (Auth и Users): система регистрации и аутентификации, права доступа, работа с токеном, система подтверждения через e-mail
- [anotherUser2](https://github.com/anotherUser2) — категории (Categories), жанры (Genres) и произведения (Titles): модели, представления и эндпойнты для них
- [nvkey](https://github.com/nvkey) — отзывы (Review) и комментарии (Comments): описание моделей, представлений, настройка эндпойнтов, определение прав доступа для запросов, рейтинги произведений

![example workflow](https://github.com/nvkey/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)