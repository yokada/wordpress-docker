## download

```
$ git clone --depth=1 --branch=master https://github.com/yokada/wordpress-docker.git
```

## change directory

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

```
$ docker-compose exec wp wp core install --url='http://localhost:8082' --title='wordpress dev site' --admin_user='admin' --admin_password='admin' --admin_email='admin@example.com' --allow-root
```

Or, Your brower can access to `http://localhost:8082` then finish installation process.

## setup wordpress via wp-cli

```
$ docker-compose exec wp wp core install --url='http://localhost:8082' --title='wordpress dev site' --admin_user='admin' --admin_password='admin' --admin_email='admin@example.com' --allow-root
```

```
$ docker-compose exec wp wp language core install ja --activate --allow-root
```

```
$ docker-compose exec wp wp option update timezone_string 'Asia/Tokyo' --allow-root
$ docker-compose exec wp wp option update date_format 'Y-m-d' --allow-root
$ docker-compose exec wp wp option update time_format 'H:i' --allow-root
```

```
$ docker-compose exec wp wp plugin delete hello.php --allow-root
```

```
$ docker-compose exec wp wp theme delete twentynineteen --allow-root
$ docker-compose exec wp wp theme delete twentyseventeen --allow-root
$ docker-compose exec wp wp theme delete twentysixteen --allow-root
```

## SSL

## Mailhog UI

`http://localhost:18025/`

## WP-CLI

## Connect to DB from Host OS
