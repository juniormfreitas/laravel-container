# laravel-container

Simplified Docker environment made to run a Laravel project

This repository will help you to run a Laravel environment using Docker.

## Getting started

You must have Docker installed in your machine in order run this application in a Docker container.

If you don't have Docker installed please visit:

[Docker Official Website](https://www.docker.com/products/docker-desktop)

Laravel utilizes Composer to manage its dependencies. Make sure to install Composer in order to install a new Laravel project after you run this environment for the first time.

If you don't have Composer installed please visit:

[Composer Official Website](https://getcomposer.org/download/)

## The Environment

This is a lightweight Laravel environment containing MySql, Nginx and a PHP instance.

The laravel app must be placed in the `./src` folder unless you change the path on the line `#44` in the `docker-composer.yml` file.

All configurations of the Nginx is placed in the `./nginx/default.conf` file and can be modified as your needs.

`Dockerfile` is responsible to download extra dependencies required by Laravel.

The application will run on the following url:
`localhost:8099` if you have any conflict regarding ports you can change the webserver's port on the line `#11` in the `docker-composer.yml` file.

## Installing Laravel

Enter into `./src` folder and execute the following command using Composer:

```
composer create-project laravel/laravel .
```

Make sure if your Docker is up and running in your computer.
Go to the root of this project where the `docker-compose.yml` file in placed then start the environment using the following command:

```
docker-compose up -d
```

then make sure that all services are running:

```
docker ps
```

Then go the browser of your choice and access the following url:

```
http://localhost:8099
```

To stop all the services you must run the following command:

```
docker-compose down
```

So you are ready to build your next project using Laravel.

## Database

In order to establish a connection into your database make sure to insert the proper values into your `.env` file. By default the connection will be established using the following values:

```
DB_HOST=laravel-mysql
DB_DATABASE=laravel-container-mysql
DB_USERNAME=homestead
DB_PASSWORD=secret
```

## PHP Artisan

To execute the command `php artisan` you must use the following command:

```
docker-compose exec laravel-php php /var/www/html/artisan
```
