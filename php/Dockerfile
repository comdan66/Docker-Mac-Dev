FROM php:7.3-apache
LABEL maintainer="comdan66@gmail.com"

# apt 與 app
RUN apt-get -qq update
RUN apt-get -qq upgrade
RUN apt-get -qqy install iputils-ping
RUN apt-get -qqy install nano
RUN apt-get -qqy install zsh
RUN apt-get -qqy install git-core

# zsh
RUN git clone https://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh \
    && cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc \
    && chsh -s /bin/zsh

RUN rm -rf /var/www/html
RUN ln -s /var/www ~/www

# 套件
RUN docker-php-ext-install -j$(nproc) pdo_mysql \
    && apt-get install -y libmagickwand-dev --no-install-recommends

RUN pecl install redis-5.1.1 \
    && pecl install imagick \
    && pecl install xdebug-2.8.1 \
    && docker-php-ext-enable redis imagick xdebug

RUN rm -rf /var/lib/apt/lists/*

RUN a2enmod rewrite

EXPOSE 80
