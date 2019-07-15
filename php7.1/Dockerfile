FROM ciandtchina/drupal-web:php7.1-apache

LABEL maintainer="jason@ciandt.com"

ENV MEMCACHED_VERSION 3.0.4

# Install PHP xdebug extension
RUN pecl install xdebug-2.6.0 && docker-php-ext-enable xdebug 

RUN apt-get update && apt-get install -y \
  libmagickwand-dev --no-install-recommends \
  && pecl install imagick \
	&& docker-php-ext-enable imagick

COPY config/* /usr/local/etc/php/conf.d/
