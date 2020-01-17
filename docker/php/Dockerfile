FROM php:7-fpm-alpine

RUN docker-php-source extract && \
  apk add --update --no-cache autoconf g++ make libzip-dev libpng-dev && \
  pecl install redis && \
  docker-php-ext-enable redis && \
  docker-php-ext-install mysqli && \
  docker-php-ext-install pdo && \
  docker-php-ext-install pdo_mysql && \
  docker-php-ext-install mbstring && \
  docker-php-ext-install tokenizer && \
  docker-php-ext-install zip && \
  docker-php-ext-install gd && \
  pecl install xdebug && \
  docker-php-ext-enable xdebug && \
  docker-php-source delete

RUN echo 'xdebug.remote_autostart=true' >> /usr/local/etc/php/php.ini && \
  echo 'xdebug.remote_mode=req' >> /usr/local/etc/php/php.ini && \
  echo 'xdebug.remote_handler=dbgp' >> /usr/local/etc/php/php.ini && \
  echo 'xdebug.remote_connect_back=1 ' >> /usr/local/etc/php/php.ini && \
  echo 'xdebug.remote_port=9000' >> /usr/local/etc/php/php.ini && \
  echo 'xdebug.remote_enable=1' >> /usr/local/etc/php/php.ini && \
  echo 'xdebug.remote_host=127.0.0.1' >> /usr/local/etc/php/php.ini

RUN rm -rf /var/cache/apk/*
