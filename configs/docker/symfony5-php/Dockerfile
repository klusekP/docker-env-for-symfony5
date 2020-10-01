FROM php:7.4-fpm

RUN pecl install mongodb

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
    composer --version

RUN usermod -u 1000 www-data

WORKDIR /var/www/symfony5