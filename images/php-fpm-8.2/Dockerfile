# create composer image to copy it to our final container later
FROM composer:latest as composer

# Basisimage php
FROM php:8.2-fpm

# install dependencies
RUN apt-get update \
    && apt-get -y install libzip-dev libicu-dev \
    && docker-php-ext-install mysqli zip intl

# install and configure xdebug
RUN  pecl install xdebug-3.2.0 \
    && docker-php-ext-enable xdebug

# copy composer binaries from composer-image
COPY --from=composer /usr/bin/composer /usr/bin/composer

