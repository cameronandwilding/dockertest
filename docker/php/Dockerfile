FROM php:5.6-apache

RUN a2enmod rewrite

RUN pecl install redis-3.1.0 \
    && pecl install xdebug \
    && pecl install xhprof-0.9.4 \
    && docker-php-ext-enable redis xdebug xhprof

RUN apt-get update && apt-get install -y libmcrypt-dev libpng12-dev libjpeg-dev libpq-dev drush mysql-client\
	&& rm -rf /var/lib/apt/lists/* \
	&& docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr \
	&& docker-php-ext-install gd mcrypt mbstring pdo pdo_mysql pdo_pgsql zip

RUN cd /root \
	&& php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
	&& php composer-setup.php
