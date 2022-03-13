FROM php:8-apache

WORKDIR /var/www/html

# PHP実行・デバッグで必要なライブラリをインストール
RUN apt-get update \
    && apt-get install -y libonig-dev libzip-dev unzip \
    && docker-php-ext-install mbstring zip bcmath \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug

# 挙動確認用ファイルと、設定ファイルをコピー
COPY ./src /var/www/html
COPY ./ini/php.ini /usr/local/etc/php/php.ini
COPY ./ini/xdebug.ini /usr/local/etc/php/conf.d/xdebug.ini