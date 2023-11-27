FROM php:8.1.9-apache

RUN apt-get update \
    && apt-get install -y git emacs vim unzip --no-install-recommends \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    && docker-php-ext-install pdo_mysql \
    && pecl install redis \
    && docker-php-ext-install opcache

COPY ./docker/php-apache/php.ini /usr/local/etc/php/conf.d/php.ini
COPY ./docker/php-apache/000-default.conf /etc/apache2/sites-available/000-default.conf
COPY --from=composer:2 /usr/bin/composer /usr/bin/composer

RUN a2enmod headers
RUN a2enmod rewrite

WORKDIR /var/www