FROM php:7.2-fpm-alpine3.10

LABEL maintainer="L-Chris@563303226@qq.com"

USER root

# ajust timezone
RUN cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

# add mirror
RUN echo "https://mirrors.aliyun.com/alpine/v3.10/main/" > /etc/apk/repositories

# install base extension
RUN docker-php-ext-install mcrypt \
  && docker-php-ext-install mysqli \
  && docker-php-ext-install pdo_mysql \
  && docker-php-ext-install mbstring \
  && docker-php-ext-install gd \
  && docker-php-ext-install bcmath \
  && docker-php-ext-install dom

# install composer
RUN curl -sS https://getcomposer.org/installer | php \
  && mv composer.phar /usr/local/bin/composer \
  && composer config -g repo.packagist composer https://packagist.phpcomposer.com