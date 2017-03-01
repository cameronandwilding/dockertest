FROM php:5.6-apache

RUN a2enmod rewrite

RUN apt-get update && apt-get install -y libmcrypt-dev libpng12-dev libjpeg-dev libpq-dev drush \
	&& rm -rf /var/lib/apt/lists/* \
	&& docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr \
	&& docker-php-ext-install gd mcrypt mbstring pdo pdo_mysql pdo_pgsql zip
