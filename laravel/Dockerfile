FROM iiiorg/laravel8-php7.4:1.0

# Setup working directory
WORKDIR /var/www

# create laravel latest version project
COPY ./laravel/src /var/www
RUN composer install
RUN cp .env.example .env
RUN php artisan key:generate

RUN composer require laravel/ui
RUN php artisan ui vue --auth
RUN npm install && npm run dev

# Run service
EXPOSE 80
CMD tail -f /dev/null
#CMD echo -e "DB_CONNECTION=mysql\nDB_HOST=$DB_HOST\nDB_PORT=$DB_PORT\nDB_DATABASE=$DB_DATABASE\nDB_USERNAME=$DB_USERNAME\nDB_PASSWORD=$DB_PASSWORD" >> .env && \
#    php artisan migrate && \
#    php artisan serve --port=80 --host=0.0.0.0 
