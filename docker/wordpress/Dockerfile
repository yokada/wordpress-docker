FROM wordpress:5.3.2-php7.2-apache

RUN curl -sSLO https://github.com/mailhog/mhsendmail/releases/download/v0.2.0/mhsendmail_linux_amd64; \
    chmod +x mhsendmail_linux_amd64; \
    mv mhsendmail_linux_amd64 /usr/local/bin/mhsendmail

COPY sendmail.ini /usr/local/etc/php/conf.d