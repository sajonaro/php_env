# php_env
php dev dockerized environment

This template allows you to bootstrap php dev environment using convention that your php source code is contained in ./source-code folder

The main idea is to use bound mount (local folder ./source-code) to share it between containers used for php development : php, nginx, composer etc.



- to create dev environment run:
```
docker compose up -d
```


- to use composer to create new project (e.g. based on laravel) run:

```
docker compose run --rm composer create-project laravel/laravel .
```

- to apply db migrations (available in source-code folder) make sure ./source-code/.env file contains db connection details specified in ./environments/mysql.env and then run:

```
docker compose run --rm artisan migrate
```