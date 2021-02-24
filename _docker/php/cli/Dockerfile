FROM php:7.4-cli

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
&& pecl install amqp uopz && docker-php-ext-enable amqp uopz \
# For PHP core }
&& curl -sS https://getcomposer.org/installer | php -- --filename=composer --install-dir=/usr/local/bin \
&& composer self-update 1.10.17 \
&& rm -rf \
    /usr/local/etc/php/php.ini-development \
    /usr/local/etc/php/php.ini-production \
    /var/lib/apt/lists/* \
    /tmp/pear

COPY /conf/php.ini /usr/local/etc/php/php.ini