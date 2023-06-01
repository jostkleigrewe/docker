ARG COMPOSER_VERSION

FROM composer:${COMPOSER_VERSION} as composer
RUN curl -sS https://get.symfony.com/cli/installer | bash

FROM php:8.2-fpm as php

RUN apt-get update && apt-get install -y libpq-dev libzip-dev libicu-dev
RUN docker-php-ext-install mysqli zip intl pdo
RUN pecl install xdebug-3.2.0
RUN docker-php-ext-enable xdebug

#RUN apt-get update && apt-get install -y libpq-dev
#RUN docker-php-ext-configure pgsql -with-pgsql=/usr/local/pgsql
#RUN docker-php-ext-install pdo pdo_pgsql
#RUN curl -sS https://get.symfony.com/cli/installer | bash
#RUN mv /root/.symfony/bin/symfony /usr/local/bin/symfony

#RUN apt update \
#    && apt install -y zlib1g-dev g++ git libicu-dev zip libzip-dev zip \
#    && docker-php-ext-install intl opcache pdo pdo_mysql \
#    && pecl install apcu \
#    && docker-php-ext-enable apcu \
#    && docker-php-ext-configure zip \
#    && docker-php-ext-install zip

# install symfony
RUN curl -sS https://get.symfony.com/cli/installer | bash \
    && mv /root/.symfony5/bin/symfony /usr/local/bin/symfony

# install composer
COPY --from=composer /usr/bin/composer /usr/local/bin/composer
COPY ./templates/*.ini /usr/local/etc/php/conf.d/
WORKDIR  /code

EXPOSE 9000

