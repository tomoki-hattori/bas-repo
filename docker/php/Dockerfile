FROM php:8.0-fpm

# 依存パッケージ install
RUN apt-get update && apt-get install -y \
    build-essential \
    libpng-dev \
    libjpeg62-turbo-dev \
    libfreetype6-dev \
    locales \
    zip \
    jpegoptim optipng pngquant gifsicle \
    vim \
    unzip \
    git \
    curl \
    npm \
    nodejs \
    libonig-dev \
    libzip-dev

# PHPの拡張機能 install
RUN docker-php-ext-install pdo_mysql zip exif pcntl gd

# composer install
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# 設定ファイル
COPY ./php.ini /usr/local/etc/php/php.ini

# ビルド時に実行コマンド
WORKDIR /usr/share/nginx/html

# ポート開放
EXPOSE 9000

# php-fpm起動
CMD ["php-fpm"]