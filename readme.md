## Simple Laravel Todo Application with Laradock
---

Simple laravel todo applicaiton.
This project has been forked from https://github.com/PJijin/Laravel-Todo-Application since 2019.3 but changed a lot.

---

[![Laravel ToDo Application](https://github.com/PJijin/Laravel-Todo-Application/blob/master/preview.png?raw=true "Laravel ToDo Application")]()


## Stack

---

* Laravel 5.7 (https://laravel.com)
* Twitter Bootstrap 4.2 (https://getbootstrap.com)
* Tailwind Css 0.7.4 (https://tailwindcss.com/)
* Fontawesome 4.7.0 (http://fontawesome.io)

## Dependencies

---

Flashy (https://github.com/mercuryseries/flashy)

## Usage

---

1. Clone or download the source code: **`git clone https://github.com/harichu/Simple-Laravel-Todo.git`**
2. CD source code folder: **`cd Simple-Laravel-Todo`**
3. Clone laradock: **`git clone https://github.com/Laradock/laradock.git`**
4. **`cd laradock`**
5. **`cp env-example .env`**
6. **`mkdir -p .laradock/data`**
7. Open file .env of laradock, find and replace with info below

>        DATA_PATH_HOST=.laradock/data

>        # Change the separator from : to ; on Windows
>        COMPOSE_PATH_SEPARATOR=;

>        PHP_VERSION=7.2

>        # If you are using Docker Sync. For `osx` use 'native_osx', for `windows` use 'unison', for `linux` docker-sync is not required
>        DOCKER_SYNC_STRATEGY=unison

>        WORKSPACE_SSH_PORT=2222 (Change port if it used)
        
>        ##=====Config Apache=====##
>        APACHE_HOST_HTTP_PORT=880 (Change port if it used)

>        APACHE_HOST_HTTPS_PORT=8443 (Change port if it used)

>        APACHE_DOCUMENT_ROOT=/var/www/public/
        
>        ##=====Config mysql=====##
>        MYSQL_VERSION=5.7

>        MYSQL_DATABASE=laravel_todo

>        MYSQL_USER=root

>        MYSQL_PASSWORD=root

>        MYSQL_PORT=33066 (Change port if it used)

>        MYSQL_ROOT_PASSWORD=root

8. **`docker-compose build apache2 mysql`**
9. **`docker-compose up -d apache2 mysql`**
10. **`docker ps`** (list docker container)
11. **`docker exec -it container_id bash`** (container id of workspace) (example: **`docker exec -it laradock_workspace_1 bash`**)
12. **`composer install`**
13. **`cp .env.example .env`**
14. **`php artisan key:generate`**
15. Setting info connect DB in file .env of laravel, example:

>        APP_NAME=Laravel
>        APP_ENV=local
>        APP_KEY=base64:dC4rB3QpkEMjl7hGntRRvSE9iTIc5AClJ6/S4zfbvk8=
>        APP_DEBUG=true
>        APP_LOG_LEVEL=debug
>        APP_URL=http://localhost

>        DB_CONNECTION=mysql
>        DB_HOST=mysql
>        DB_PORT=3306
>        DB_DATABASE=laravel_todo
>        DB_USERNAME=root
>        DB_PASSWORD=root

>        BROADCAST_DRIVER=log
>        CACHE_DRIVER=file
>        SESSION_DRIVER=file
>        QUEUE_DRIVER=sync

>        REDIS_HOST=127.0.0.1
>        REDIS_PASSWORD=null
>        REDIS_PORT=6379

>        MAIL_DRIVER=smtp
>        MAIL_HOST=smtp.mailtrap.io
>        MAIL_PORT=2525
>        MAIL_USERNAME=null
>        MAIL_PASSWORD=null
>        MAIL_ENCRYPTION=null

>        PUSHER_APP_ID=
>        PUSHER_APP_KEY=
>        PUSHER_APP_SECRET=

16. **`php artisan migrate`**
17. **`composer dump-autoload`**
18. **`php artisan db:seed`**
