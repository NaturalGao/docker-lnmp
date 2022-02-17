FROM php:8.1-fpm

RUN apt-get clean
RUN apt-get update

#   安装常用的包
RUN apt-get install -y \
    vim \
    curl \
    net-tools \
    iputils-ping \
    procps

#   安装 REDIS/XDEBUG

RUN pecl install redis
RUN docker-php-ext-enable redis

#   使用镜像中的生产环境 php.ini 配置文件
RUN mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini"

# 添加自定义配置文件
COPY ./config/php.ini $PHP_INI_DIR/conf.d/php.ini

WORKDIR /var/www