FROM mysql:5.7

RUN ln -sf /usr/share/zoneinfo/Japan /etc/localtime

COPY ./custom.cnf /etc/mysql/conf.d/

EXPOSE 3306
