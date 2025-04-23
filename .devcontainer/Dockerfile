FROM nestybox/ubuntu-jammy-systemd-docker:latest

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Install PHP 8.4 and required extensions
RUN apt-get update && apt-get install -y \
    software-properties-common \
    && add-apt-repository ppa:ondrej/php -y \
    && apt-get update \
    && apt-get install -y \
    php8.4 \
    php8.4-fpm \
    php8.4-mysql \
    php8.4-mbstring \
    php8.4-xml \
    php8.4-zip \
    php8.4-gd \
    php8.4-curl \
    php8.4-bcmath \
    libpng-dev \
    libfreetype6-dev \
    zip \
    unzip \
    git \
    curl \
    nano \
    net-tools \
    sudo \
    && update-alternatives --set php /usr/bin/php8.4 \
    && php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php composer-setup.php --install-dir=/usr/local/bin --filename=composer \
    && php -r "unlink('composer-setup.php');"

# Install Statamic CLI
RUN composer global require statamic/cli
RUN export PATH="~/.config/composer/vendor/bin/":$PATH

# Install Node.js and npm for Laravel frontend (e.g., Vite)
RUN curl -fsSL https://deb.nodesource.com/setup_22.x | bash - \
    && apt-get install -y nodejs \
    && npm install -g npm

# Start systemd (required by Nestybox for system-level services)
CMD ["/sbin/init"]