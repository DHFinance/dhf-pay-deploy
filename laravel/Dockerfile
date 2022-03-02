FROM php:7.4-fpm

# Arguments defined in docker-compose.yml
ARG user
ARG uid


RUN apt-get update \
  && apt-get install -y \
             nano \
             git \
             libfreetype6-dev \
             libjpeg62-turbo-dev \
             libmcrypt-dev \
             libpng-dev \
             zlib1g-dev \
             libxml2-dev \
             libzip-dev \
             libonig-dev \
             graphviz \
             libcurl4-openssl-dev \
             pkg-config \
             curl \
             libpq-dev \
             zip \
             unzip




# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Install PHP extensions
RUN apt-get install -y libpq-dev && \
    docker-php-ext-install pgsql pdo_pgsql  mbstring exif pcntl bcmath gd

# Get latest Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Create system user to run Composer and Artisan Commands
#RUN useradd -G www-data,root -u $uid -d /home/$user $user
#RUN mkdir -p /home/$user/.composer && \
#    chown -R $user:$user /home/$user

# Set working directory
WORKDIR /app

COPY ./* /app
USER $user
