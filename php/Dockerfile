FROM php:8.0-fpm

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
    unzip

#   安装 REDIS/XDEBUG
RUN pecl install redis
RUN docker-php-ext-enable redis
RUN docker-php-ext-install zip

#   使用镜像中的生产环境 php.ini 配置文件
RUN mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini"

# 添加自定义配置文件
COPY ./config/php.ini $PHP_INI_DIR/conf.d/php.ini

# 指定工作目录
WORKDIR /www