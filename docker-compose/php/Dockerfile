FROM php:7.1.27-fpm-jessie

RUN curl -sL https://deb.nodesource.com/setup_4.x | bash -
RUN apt-get update
RUN apt-get install -y zlib1g-dev libicu-dev g++ libxml++2.6-dev nodejs git zip libpng-dev libzip-dev
RUN apt-get install -y \
  libpng-dev \
  libfreetype6-dev \
  libjpeg-dev \
  libxpm-dev \
  libxml2-dev \
  libxslt-dev \
  libmcrypt-dev \
  libwebp-dev
RUN docker-php-ext-configure gd \
    --with-freetype-dir=/usr/include/ \
    --with-jpeg-dir=/usr/include/ \
    --with-xpm-dir=/usr/include \
    --with-webp-dir=/usr/include/
RUN docker-php-ext-install gd
RUN npm install -g bower
RUN docker-php-ext-install pdo
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install intl
RUN docker-php-ext-install bcmath
RUN docker-php-ext-install soap
RUN docker-php-ext-install pcntl
RUN docker-php-ext-install shmop
RUN docker-php-ext-install zip
RUN docker-php-ext-install exif
RUN pecl install zip
RUN curl http://getcomposer.org/composer.phar > /usr/local/bin/composer && chmod +x /usr/local/bin/composer