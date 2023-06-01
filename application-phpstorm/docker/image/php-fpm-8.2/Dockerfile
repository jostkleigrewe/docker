ARG COMPOSER_VERSION

FROM composer:${COMPOSER_VERSION} as composer


FROM php:8.2-fpm as php

RUN apt-get update && apt-get install -y libpq-dev libzip-dev libicu-dev
RUN docker-php-ext-install mysqli zip intl pdo
RUN pecl install xdebug-3.2.0
RUN docker-php-ext-enable xdebug

#RUN apt-get update && apt-get install -y libpq-dev
#RUN docker-php-ext-configure pgsql -with-pgsql=/usr/local/pgsql
#RUN docker-php-ext-install pdo pdo_pgsql


COPY --from=composer /usr/bin/composer /usr/local/bin/composer
COPY ./templates/*.ini /usr/local/etc/php/conf.d/
WORKDIR  /code

EXPOSE 9000

