## start containers

```
$ mv .env.sample .env
```

```
$ docker-compose up -d --build
```

## setup wordpress via wp-cli

```
$ docker-compose run wp-cli core install --url='http://localhost:8080' --title='wordpress dev site' --admin_user='admin' --admin_password='admin' --admin_email='admin@example.com'
```

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

## Refs

- [ DockerでWP-CLI入りのWordpressコンテナを作る - Qiita ]( https://qiita.com/Ayutanalects/items/4978ef104fd1dcde2b0e )

