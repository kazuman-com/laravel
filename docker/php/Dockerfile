FROM php:7.0.6-fpm

RUN apt-get update && \
    apt-get install -y zip zlib1g-dev libmcrypt-dev curl wget vim sudo && \
    rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-install mbstring mysqli pdo_mysql zip

# install composer 
WORKDIR /tmp
RUN php -r "readfile('https://getcomposer.org/installer');" > composer-setup.php && \
    php -r "if (hash_file('SHA384', 'composer-setup.php') === 'a52be7b8724e47499b039d53415953cc3d5b459b9d9c0308301f867921c19efc623b81dfef8fc2be194a5cf56945d223') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" && \
    php composer-setup.php && \
    php -r "unlink('composer-setup.php');" && \
    mv composer.phar /usr/local/bin/composer

# install Laravel framework
WORK /root
RUN composer global require "laravel/installer"
