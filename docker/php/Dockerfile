FROM php:7.3.33-bullseye

# Set the working directory
WORKDIR /esmigrations

# Install system dependencies
RUN apt-get update && apt-get install -y \
    git \
    zip \
    unzip \
    zlib1g-dev \
    libzip-dev \
    && docker-php-ext-configure zip \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Install PHP extensions
RUN docker-php-ext-install \
    mbstring \
    zip

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
