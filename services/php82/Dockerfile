ARG PHP_IMAGE
FROM ${PHP_IMAGE}

# 安装扩展
RUN apt-get update \
    # 相关依赖必须手动安装
    && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng-dev \
    # 安装扩展
    && docker-php-ext-install iconv \
    # 如果安装的扩展需要自定义配置时
    && docker-php-ext-configure gd --enable-gd --with-freetype --with-jpeg \
    && docker-php-ext-install gd

RUN docker-php-ext-install pdo pdo_mysql

RUN docker-php-ext-install mysqli

# 安装 composer
RUN curl -o /usr/bin/composer https://mirrors.aliyun.com/composer/composer.phar && chmod +x /usr/bin/composer

COPY ./www/index.php /www/holovision.com/public/

WORKDIR /www