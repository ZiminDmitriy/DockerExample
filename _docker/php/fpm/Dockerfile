FROM php:7.4-fpm

RUN \
# For PHP core {
apt-get update && apt-get install -y \
# For PHP amqp-extension {
    librabbitmq-dev \
# For PHP amqp-extension }
# For PHP zip-extension {
    libzip-dev \
# For PHP zip-extension }
&& docker-php-ext-install \
# For PHP amqp-extension {
    bcmath \
# For PHP amqp-extension }
    zip \
&& pecl install amqp && docker-php-ext-enable amqp \
# For PHP core }
&& rm -rf \
    /usr/local/etc/php/php.ini-development \
    /usr/local/etc/php/php.ini-production \
    /usr/local/etc/php-fpm.d/www.conf.default \
    /usr/local/etc/php-fpm.d/www.conf \
    /usr/local/etc/php-fpm.conf.default \
    /usr/local/etc/php-fpm.conf \
    /var/lib/apt/lists/* \
    /tmp/pear

COPY /conf/php.ini /usr/local/etc/php/php.ini
COPY /conf/www.conf /usr/local/etc/php-fpm.d/www.conf
COPY /conf/php-fpm.conf /usr/local/etc/php-fpm.conf