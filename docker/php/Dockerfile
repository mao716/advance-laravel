# Laravel 11 に合わせて 8.2
FROM php:8.1-fpm

COPY php.ini /usr/local/etc/php/

RUN apt-get update \
	&& apt-get install -y --no-install-recommends \
	default-mysql-client \
	zlib1g-dev \
	libzip-dev \
	libonig-dev \
	unzip \
	&& docker-php-ext-install pdo_mysql zip mbstring \
	&& rm -rf /var/lib/apt/lists/*

RUN curl -sS https://getcomposer.org/installer | php \
	&& mv composer.phar /usr/local/bin/composer

WORKDIR /var/www
