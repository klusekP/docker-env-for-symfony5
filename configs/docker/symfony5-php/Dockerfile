FROM php:7.4-fpm

RUN pecl install mongodb
RUN echo "extension=mongodb.so" >> `php --ini | grep "Loaded Configuration" | sed -e "s|.*:\s*||"`
RUN apt-get update && apt-get install -y curl git zip

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
    composer --version && \
    docker-php-ext-enable mongodb && apt-get clean

RUN usermod -u 1000 www-data

WORKDIR /var/www/symfony5
