FROM php:7.4-fpm

RUN apt-get update && apt-get install -y \
    unzip git libicu-dev libzip-dev zip \
    && docker-php-ext-install intl pdo pdo_mysql zip

COPY ./login.php /var/www/html/login.php
COPY ./welcome.php /var/www/html/welcome.php
COPY ./logout.php /var/www/html/logout.php
WORKDIR /var/www/html

RUN chown -R www-data:www-data /var/www/html

EXPOSE 9000

CMD ["php-fpm"]
