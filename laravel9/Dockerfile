FROM php:8-apache

WORKDIR /var/www/project

ARG NODE_VERSION=16

RUN curl -sL https://deb.nodesource.com/setup_${NODE_VERSION}.x | bash -

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN apt-get update && apt-get install -y openssl zip libzip-dev supervisor cron nodejs

RUN docker-php-ext-install bcmath zip pdo_mysql exif

RUN a2enmod rewrite && service apache2 restart

COPY apache.conf /etc/apache2/sites-available/000-default.conf

COPY supervisor.conf /etc/supervisor/conf.d/supervisor.conf

COPY crontab /etc/crontab

COPY entrypoint.sh /var/www/entrypoint.sh

ENTRYPOINT ["sh", "/var/www/entrypoint.sh"]
