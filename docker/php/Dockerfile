FROM php:7.0.6-fpm

RUN apt-get update && \
    apt-get install -y zip zlib1g-dev libmcrypt-dev curl wget vim sudo && \
    rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-install mbstring mysqli pdo_mysql zip

# install composer 
WORKDIR /tmp
RUN php -r "readfile('https://getcomposer.org/installer');" > composer-setup.php && \
    php composer-setup.php && \
    php -r "unlink('composer-setup.php');" && \
    mv composer.phar /usr/local/bin/composer

# install Laravel framework
WORKDIR /root
RUN composer global require "laravel/installer"
