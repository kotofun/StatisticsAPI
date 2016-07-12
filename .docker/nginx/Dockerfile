FROM alpine:3.4

RUN apk add --update nginx
RUN rm -rf /var/cache/apk/* && rm -rf /tmp/*

ADD nginx.conf /etc/nginx/
ADD statistics.conf /etc/nginx/conf.d/

RUN echo "upstream php-upstream { server php:9000; }" > /etc/nginx/conf.d/upstream.conf

CMD ["nginx"]

RUN adduser -D -g '' -G www-data www-data

EXPOSE 80
EXPOSE 443
