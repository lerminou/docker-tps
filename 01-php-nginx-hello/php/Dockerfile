FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -y php-fpm && \
    apt-get clean

RUN sed -i 's|^listen = .*|listen = 0.0.0.0:9000|' /etc/php/8.3/fpm/pool.d/www.conf

CMD ["php-fpm8.3", "-F"]
