FROM ciandtchina/drupal-web:php7.1-apache

LABEL maintainer="jason@ciandt.com"

ENV MEMCACHED_VERSION 3.0.4

# Install PHP xdebug extension
RUN pecl install xdebug-2.6.0 && docker-php-ext-enable xdebug 

RUN apt-get update && apt-get install -y libpng-dev 
RUN apt-get install -y \
    libwebp-dev \
    libjpeg62-turbo-dev \
    libpng-dev libxpm-dev \
    libfreetype6-dev

RUN docker-php-ext-configure gd \
    --with-gd \
    --with-webp-dir \
    --with-jpeg-dir \
    --with-png-dir \
    --with-zlib-dir \
    --with-xpm-dir \
    --with-freetype-dir \
    --enable-gd-native-ttf

RUN docker-php-ext-install gd
