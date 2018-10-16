FROM php:7.2-fpm

RUN apt-get update 
RUN apt-get install -f --no-install-recommends -y git curl wget sudo libfreetype6-dev libjpeg62-turbo-dev libmcrypt-dev libxml2-dev libpq-dev libpq5 mysql-client ssl-cert libicu-dev

RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/

RUN docker-php-ext-install -j$(nproc) mbstring zip gd xml pdo pdo_pgsql pdo_mysql soap intl
RUN rm -r /var/lib/apt/lists/*