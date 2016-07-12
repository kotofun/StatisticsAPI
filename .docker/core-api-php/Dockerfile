FROM php:alpine

RUN echo http://nl.alpinelinux.org/alpine/edge/testing >> /etc/apk/repositories
RUN apk add --update \
     libpq \
     shadow \
     git

WORKDIR /opt/app

RUN git clone https://github.com/kursomir/CoreAPI.git /opt/app

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin/ --filename=composer
RUN composer install

ADD .env /opt/app/.env
