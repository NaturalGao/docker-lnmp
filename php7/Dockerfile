FROM php:7.3-fpm

RUN apt-get clean
RUN apt-get update

#   安装常用的包
RUN apt-get install -y \
    vim \
    curl \
    net-tools \
    iputils-ping \
    procps \ 
    git \
    netplan.io \
    zlib1g-dev  \
    libzip-dev  \
    unzip \ 
    libpng-dev

#   安装 REDIS/XDEBUG
RUN pecl install redis
RUN docker-php-ext-enable redis
RUN docker-php-ext-install zip
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install bcmath

#   使用镜像中的生产环境 php.ini 配置文件
RUN mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini"

# 指定工作目录
WORKDIR /www