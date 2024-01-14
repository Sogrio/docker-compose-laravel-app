FROM php:8.1.0-fpm

WORKDIR /var/www/html

COPY  composer.json /var/www/html/composer.json
COPY  composer.lock /var/www/html/composer.lock

COPY . /var/www/html/

RUN apt-get update && apt-get install -y \
    git \
    unzip \
    && docker-php-ext-install pdo_mysql

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Installer Node.js et npm
RUN curl -sL https://deb.nodesource.com/setup_18.x | bash - \
    && apt-get install -y nodejs

RUN npm install

# Installation des dépendances Composer
RUN composer install

# Installation des dépendances NPM
RUN npm install

# Exécution des commandes Laravel
RUN php artisan key:generate
RUN php artisan migrate:fresh --seed

# Exemple de commande npm Laravel
RUN npm run build
