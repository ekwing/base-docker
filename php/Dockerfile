FROM php:7.2-fpm-alpine3.9

LABEL maintainer="L-Chris@563303226@qq.com"

USER root

# add mirror
RUN echo "https://mirrors.aliyun.com/alpine/v3.9/main/" > /etc/apk/repositories

RUN set -x \
  && apk add --no-cache libstdc++ libxml2-dev \
  && apk add --no-cache --virtual .build-deps \
    binutils-gold \
    curl \
    g++ \
    gcc \
    gnupg \
    linux-headers \
    make \
    python \
    tzdata

# ajust timezone
RUN cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

# install base extension
RUN docker-php-ext-install mysqli \
  && docker-php-ext-install pdo_mysql \
  && docker-php-ext-install bcmath

# install composer
RUN curl -sS https://install.phpcomposer.com/installer | php \
  && mv composer.phar /usr/local/bin/composer \
  && composer config -g repo.packagist composer https://packagist.phpcomposer.com

# clean up
RUN apk del .build-deps \
  && rm -rf \
    /tmp/* \
    /var/cache/apk/* \
    /usr/share/man