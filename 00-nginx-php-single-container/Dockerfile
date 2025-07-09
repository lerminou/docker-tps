FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y nginx php-fpm && apt-get clean

# Configure PHP-FPM pour écouter en socket
RUN sed -i 's|^listen = .*|listen = /run/php/php8.3-fpm.sock|' /etc/php/8.3/fpm/pool.d/www.conf


COPY hello.php /var/www/html/index.php
COPY default /etc/nginx/sites-enabled/default

CMD service php8.3-fpm start && nginx -g 'daemon off;'
