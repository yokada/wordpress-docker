## download

```
$ git clone --depth=1 --branch=master https://github.com/yokada/wordpress-docker.git
```

change directory:

```
$ cd wordpress-docker
```

## prepare config files

```
$ cp .env.sample .env
$ cp docker/mysql/.env.sample docker/mysql/.env
$ cp docker/wordpress/.env.sample docker/wordpress/.env
```

## start containers

```
$ docker-compose up -d --build
```

## install process to complete

Brower access to `http://localhost:8080` and finish installation process.

## setup wordpress via wp-cli

<!--
```
$ docker-compose run wp-cli core install --url='http://localhost:8080' --title='wordpress dev site' --admin_user='admin' --admin_password='admin' --admin_email='admin@example.com'
```
-->

```
$ docker-compose run wp-cli language core install ja --activate
```

```
$ docker-compose run wp-cli option update timezone_string 'Asia/Tokyo'
$ docker-compose run wp-cli option update date_format 'Y-m-d'
$ docker-compose run wp-cli option update time_format 'H:i'
```

```
$ docker-compose run wp-cli plugin delete hello.php
```

```
$ docker-compose run wp-cli theme delete twentynineteen
$ docker-compose run wp-cli theme delete twentyseventeen
$ docker-compose run wp-cli theme delete twentysixteen
```
