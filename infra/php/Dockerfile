FROM php:8.2-fpm-buster

ENV COMPOSER_ALLOW_SUPERUSER=1 \
  COMPOSER_HOME=/composer

COPY --from=composer:2.4 /usr/bin/composer /usr/bin/composer

RUN apt-get update 
# RUN apt-get -y install --no-install-recommends git unzip libzip-dev libicu-dev libonig-dev
RUN apt-get clean 
RUN rm -rf /var/lib/apt/lists/* 
RUN docker-php-ext-install intl pdo_mysql zip bcmath

COPY ./php.ini /usr/local/etc/php/php.ini

WORKDIR /data
