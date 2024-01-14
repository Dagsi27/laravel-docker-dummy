FROM php:8.2.7-fpm

RUN apt-get update \
    && apt-get upgrade -y \
    nano \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    curl \ 
    zlib1g-dev \
    libzip-dev

# Install PHP extensions
RUN docker-php-ext-install bcmath exif gd mbstring pcntl pdo_mysql sockets opcache zip mysqli 

RUN curl -sSk https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer 
RUN curl -sS https://get.symfony.com/cli/installer | bash
ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/

COPY . /var/www
WORKDIR /var/www