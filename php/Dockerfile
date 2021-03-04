FROM php:8.0-apache

# Install Xdebug
RUN apt-get update && apt-get install -y vim \
    && pecl install xdebug && docker-php-ext-enable xdebug

# Configure PHP
RUN echo "\
    short_open_tag = On" > /usr/local/etc/php/php.ini

# Configure xDebug
RUN echo "\n\
    xdebug.mode=debug\n\
    xdebug.discover_client_host=1\n\
    xdebug.client_port=9000\n\
    xdebug.XDEBUG_SESSION=VSCODE \n\
    xdebug.log=/var/www/html/xdebug.log\n\
    ">> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini

WORKDIR /var/www/html

