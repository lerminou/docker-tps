FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    php php-fpm php-cli php-mbstring php-xml php-intl php-mysql php-curl php-zip unzip git curl && \
    apt-get clean

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN sed -i 's|^listen = .*|listen = 0.0.0.0:9000|' /etc/php/8.3/fpm/pool.d/www.conf

CMD ["php-fpm8.3", "-F"]
