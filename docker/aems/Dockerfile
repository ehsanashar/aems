FROM php:8.2-fpm

# Install system dependencies
RUN apt-get update && apt-get install -y \
    git \
    curl \
    unzip \
    libzip-dev \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    libcurl4-openssl-dev \
    libpq-dev \
    libmcrypt-dev \
    && docker-php-ext-install pdo pdo_mysql mbstring exif pcntl bcmath gd xml

# Install Composer
COPY --from=composer:2 /usr/bin/composer /usr/bin/composer

# Set working directory
WORKDIR /var/www

# Copy existing application directory contents
# (Optional: Docker Compose will mount the volume anyway)
# COPY . /var/www

# Set recommended permissions
RUN chown -R www-data:www-data /var/www \
    && chmod -R 755 /var/www

# Expose port (not strictly necessary for PHP-FPM)
EXPOSE 9000
