FROM wordpress:5.3.2-php7.2-apache

RUN curl -sSLO https://github.com/mailhog/mhsendmail/releases/download/v0.2.0/mhsendmail_linux_amd64; \
    chmod +x mhsendmail_linux_amd64; \
    mv mhsendmail_linux_amd64 /usr/local/bin/mhsendmail

RUN curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar \
    && chmod +x wp-cli.phar \
    && mv wp-cli.phar /usr/local/bin/wp

RUN pecl install xdebug \
    && docker-php-ext-enable xdebug

COPY sendmail.ini /usr/local/etc/php/conf.d
COPY xdebug.ini /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini
COPY localhost.crt /etc/ssl/certs/localhost.crt
COPY localhost.key /etc/ssl/private/localhost.key
COPY default-ssl.conf /etc/apache2/sites-available/default-ssl.conf
COPY --from=composer /usr/bin/composer /usr/bin/composer

RUN a2enmod ssl \
    && a2ensite default-ssl

EXPOSE 80 443
CMD ["apache2-foreground"]
