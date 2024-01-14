FROM php:7.4-fpm

#WORKDIR /var/www/html

COPY . /var/www/html/

RUN apt-get update && apt-get install -y \
    git \
    unzip \
    nodejs \
    npm \
    && docker-php-ext-install pdo_mysql

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN npm install

# Installation des dépendances Composer
RUN composer install

# Installation des dépendances NPM
RUN npm install

# Exécution des commandes Laravel
RUN php artisan key:generate
RUN php artisan migrate:fresh --seed

# Autres étapes de configuration et de build
# ...

# Exemple de commande artisan Laravel
RUN php artisan key:generate

# Exemple de commande npm Laravel
RUN npm run build
