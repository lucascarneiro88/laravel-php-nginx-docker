# Definindo a imagem base do PHP
FROM php:8.3.14-fpm-alpine 

# Instalando as extensões do PHP necessárias e dependências de build
RUN apk update && apk add --no-cache \
    libpng-dev \
    libjpeg-turbo-dev \
    freetype-dev \
    libzip-dev \
    git \
    unzip \
    icu-dev \
    libxml2-dev \
    openssl-dev \
    bash \
    --virtual .build-deps gcc g++ make

# Instalando extensões PHP necessárias
RUN docker-php-ext-install gd pdo_mysql

# Instalando nodejs, npm e libs para sqlite (resolve erro de relocação)
RUN apk add --no-cache nodejs-current npm sqlite-libs


# Adicionando o composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
