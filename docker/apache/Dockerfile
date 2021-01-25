FROM php:7.4-apache

RUN apt-get update
RUN apt-get install -y g++ libicu-dev libjpeg-dev libpng-dev libxml2-dev libxslt1-dev libzip-dev zlib1g-dev

RUN docker-php-ext-configure gd --with-jpeg
RUN docker-php-ext-configure intl

RUN docker-php-ext-install bcmath gd intl pdo pdo_mysql soap sockets xsl zip

COPY sites-available/000-default.conf /etc/apache2/sites-available/

RUN a2enmod rewrite

#CMD [ "chown", "-R", "www-data:www-data", "/var/www/html" ]

#php -d memory_limit=-1 bin/magento setup:install --db-host="mysql" --db-name="magento" --db-user="root" --db-password="test" --language="en_US" --currency="USD" --timezone="America/New_York" --elasticsearch-host="elasticsearch" --elasticsearch-port="9200"
