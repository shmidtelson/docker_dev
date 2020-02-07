FROM nginx

ADD ./etc/nginx/default.conf /etc/nginx/conf.d/default.conf

RUN chown -R www-data:www-data /var/www

WORKDIR /var/www
