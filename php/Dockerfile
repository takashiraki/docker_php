FROM php:8.3-apache

RUN apt-get update \
    && apt-get install -y unzip libpq-dev git vim gh msmtp msmtp-mta \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug \
    && docker-php-ext-install mysqli pdo_mysql opcache \
    && (type -p wget >/dev/null || (apt-get update && apt-get install wget -y)) \
    && mkdir -p -m 755 /etc/apt/keyrings \
    && out=$(mktemp) && wget -nv -O$out https://cli.github.com/packages/githubcli-archive-keyring.gpg \
    && cat $out > /etc/apt/keyrings/githubcli-archive-keyring.gpg \
    && chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
    && mkdir -p -m 755 /etc/apt/sources.list.d \
    && echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" > /etc/apt/sources.list.d/github-cli.list

COPY php.ini /usr/local/etc/php/

WORKDIR /var/www/html