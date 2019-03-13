FROM php:7.2-fpm-stretch

RUN apt-get update && apt-get install -y libmcrypt-dev git\
    mysql-client libmagickwand-dev --no-install-recommends \
    && pecl install imagick \
    && docker-php-ext-enable imagick \
    && docker-php-ext-install mbstring mysqli pdo_mysql gd zip \
    && apt-get install unzip

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install Nodejs and NPM
RUN apt-get update -yq \
    && apt-get install curl gnupg -yq \
    && curl -sL https://deb.nodesource.com/setup_10.x | bash \
    && apt-get install nodejs -yq

CMD ["php-fpm"]

EXPOSE 9000
