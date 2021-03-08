FROM php:7.4-fpm

COPY docker/app/config/php.ini /usr/local/etc/php/php.ini

WORKDIR /var/www

# Add user for the application
RUN groupadd -g 1000 www
RUN useradd -u 1000 -ms /bin/bash -g www www

# Copy existing application directory contents
COPY . .

# Give permission
RUN chown -R www:www /var/www
RUN chmod -R 777 /var/www

USER www

EXPOSE 9000
CMD [ "php-fpm" ]