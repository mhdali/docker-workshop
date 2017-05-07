FROM alpine:3.5

COPY ./pkgs/s6-overlay-amd64.tar.gz /tmp/
RUN tar xzf /tmp/s6-overlay-amd64.tar.gz -C /
CMD ["/init"]

RUN apk --no-cache add \
                openssl \
                ca-certificates \
                apache2 \
                apache2-utils \
                apache2-proxy \
                php7 \
                php7-fpm \
                php7-mysqli \
                php7-pdo_mysql \
                php7-zlib \
        && mkdir -p /run/apache2 \
        && rm -f /etc/apache2/conf.d/proxy.conf

COPY ./etc/services.d /etc/services.d/
COPY ./etc/cont-init.d /etc/cont-init.d/
COPY ./etc/fix-attrs.d /etc/fix-attrs.d/
COPY ./etc/apache2 /etc/apache2/conf.d/
COPY ./etc/pool.d /etc/php7/php-fpm.d/

COPY ./wp /var/www/localhost/htdocs/wp
