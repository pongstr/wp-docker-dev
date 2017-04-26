FROM wordpress:4.7.4-php7.1-fpm

RUN mkdir -p /var/www/html/wp-content/themes/dev

RUN chmod +x /usr/local/bin/docker-entrypoint.sh

# ENTRYPOINT resets CMD
ENTRYPOINT ["docker-entrypoint.sh"]
CMD ["php-fpm"]
