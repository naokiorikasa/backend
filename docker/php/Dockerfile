# 最新のPHP-FPMイメージをベースにする
FROM php:8.4-fpm

# 必要なライブラリをインストール
RUN apt-get update && apt-get install -y \
    git \
    unzip \
    libzip-dev \
    libpng-dev \
    libjpeg62-turbo-dev \
    libfreetype6-dev \
    locales \
    zip \
    jpegoptim optipng pngquant gifsicle \
    vim \
    nodejs \
    npm

# PHP拡張機能をインストール
RUN docker-php-ext-install pdo_mysql pcntl bcmath gd zip

# Composerをインストール
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# 作業ディレクトリを設定
WORKDIR /var/www/html
