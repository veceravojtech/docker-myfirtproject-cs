FROM php:7.2-fpm-alpine

ARG USER_NAME

RUN adduser -D -u 1000 ${USER_NAME}
RUN apk upgrade --update
RUN apk add --update alpine-sdk
RUN apk add --no-cache --virtual .build-deps
RUN apk add autoconf gcc pkgconf libressl-dev libsasl libressl  libmcrypt-dev icu icu-libs icu-dev imap-dev libxml2-dev libxslt-dev curl-dev .build-deps coreutils freetype-dev libjpeg-turbo-dev libltdl libpng-dev
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php composer-setup.php \
    && php -r "unlink('composer-setup.php');" \
    && mv composer.phar /usr/bin/composer
RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/
RUN docker-php-ext-install intl
RUN docker-php-ext-install pdo
RUN docker-php-ext-install imap
RUN docker-php-ext-install xml
RUN docker-php-ext-install xsl
RUN docker-php-ext-install zip
RUN docker-php-ext-install bcmath
RUN docker-php-ext-install curl
RUN docker-php-ext-install json
RUN docker-php-ext-install mbstring
RUN docker-php-ext-install exif
RUN docker-php-ext-install gd
RUN docker-php-ext-install opcache
RUN docker-php-ext-install pdo_mysql

WORKDIR "/var/www/mujprojekt"
