FROM php:8.1-fpm
RUN apt-get update && apt-get install -y \
    git \
    curl \
    libpng-dev \
    libjpeg-dev \
    && docker-php-ext-install pdo pdo_mysql
WORKDIR /var/www
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer
COPY . /var/www
COPY --chown=www-data:www-data . /var/www
USER www-data
EXPOSE 8000
CMD ["php-fpm"]
