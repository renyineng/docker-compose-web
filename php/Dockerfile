FROM php:7.3-fpm
MAINTAINER renyineng 7332039@qq.com
RUN apt-get update 
RUN apt-get install -y zip unzip
RUN apt-get install -y apt-utils
RUN apt-get install -y libzip-dev
RUN pecl install zip 
RUN docker-php-ext-enable zip
RUN docker-php-ext-install pdo_mysql \
    && docker-php-ext-install bcmath \
    && docker-php-ext-install mysqli

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
    && docker-php-ext-install -j$(nproc) iconv \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd

ADD bin/composer /usr/local/bin/composer
RUN apt-get install -y git
RUN composer config -g repo.packagist composer https://mirrors.aliyun.com/composer/
#此处可以设置git用户
#RUN git config --global user.name "author" && git config --global user.email "author@admin.com" 

WORKDIR /data/www
RUN composer global require laravel/installer
ENV PATH ~/.composer/bin:$PATH