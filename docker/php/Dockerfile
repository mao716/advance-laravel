# Laravel 11 要件を満たす
FROM php:8.2-fpm

# php.ini を反映（ファイル名 php.ini のままでOK）
COPY php.ini /usr/local/etc/php/php.ini

# 必要パッケージ & PHP拡張
RUN apt-get update \
	&& apt-get install -y --no-install-recommends \
	mariadb-client \
	zlib1g-dev \
	libzip-dev \
	libonig-dev \
	unzip \
	&& docker-php-ext-install pdo_mysql zip mbstring \
	&& rm -rf /var/lib/apt/lists/*

# Composerは公式イメージからコピー（速くて安全）
COPY --from=composer:2 /usr/bin/composer /usr/local/bin/composer

WORKDIR /var/www
