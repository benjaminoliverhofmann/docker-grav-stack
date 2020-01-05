FROM alpine:latest


LABEL maintainer="hb@beohof.de"

RUN adduser -D -g 'www' www

RUN apk add --no-cache nginx \
supervisor \
composer \
git \
php7 \
php7-fpm  \
php7-zip \
php7-curl \
php7-dom \
php7-tokenizer \
php7-gd \
php7-xml \
php7-xmlwriter \
 php7-simplexml \
php7-session \
php7-ctype \
php7-mbstring \
php7-json \
php7-openssl

RUN mkdir /www && \
chown -R www:www /var/lib/nginx && \
chown -R www:www /www


COPY config/nginx.conf /etc/nginx/nginx.conf
COPY config/supervisord.conf /etc/supervisord.conf
COPY config/php-fpm.conf /etc/php7/php-fpm.conf
COPY config/php.ini /etc/php7/php.ini

ENTRYPOINT ["supervisord"]
EXPOSE 80
