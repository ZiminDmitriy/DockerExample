FROM nginx:1.19.3

RUN \
rm \
    /etc/nginx/nginx.conf \
    /etc/nginx/conf.d/default.conf \
&& mkdir \
    /var/www \
    /var/www/html

COPY /conf/nginx.conf /etc/nginx/nginx.conf
COPY /conf/default.conf /etc/nginx/conf.d/default.conf