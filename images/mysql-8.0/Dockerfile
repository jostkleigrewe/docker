FROM mysql/mysql-server:8.0

ENV MYSQL_ALLOW_EMPTY_PASSWORD="yes"
ENV MYSQL_ROOT_PASSWORD=docker
ENV MYSQL_DATABASE=docker
ENV MYSQL_USER=docker
ENV MYSQL_PASSWORD=changeme

COPY setup.sql /docker-entrypoint-initdb.d/
