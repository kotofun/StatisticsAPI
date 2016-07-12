FROM php:fpm-alpine

RUN echo http://nl.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories
RUN apk add --update \
     libpq \
     shadow

RUN docker-php-ext-install \
    pdo_pgsql

RUN rm -rf /var/cache/apk/* && rm -rf /tmp/*

ADD statistics.ini /etc/php7/fpm/conf.d/
ADD statistics.ini /etc/php7/cli/conf.d/

ADD statistics.pool.conf /etc/php7/fpm/pool.d/

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin/ --filename=composer

RUN usermod -u 1000 www-data

WORKDIR /var/www

VOLUME /var/www

USER www-data
