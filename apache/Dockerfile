FROM ubuntu/apache2
COPY ./my-default-ssl.conf /etc/apache2/sites-available/default-ssl.conf
COPY ./my-apache2.conf /etc/apache2/apache2.conf
COPY ./apache_ssl.key /etc/ssl/private/apache_ssl.key
COPY ./apache_ssl.crt /etc/ssl/certs/apache_ssl.crt
COPY ./.htaccess /var/www/html/.htaccess
RUN a2enmod ssl
RUN a2enmod rewrite
RUN a2ensite default-ssl.conf
RUN a2enmod proxy
RUN a2enmod proxy_http
RUN a2enmod proxy_balancer
RUN service apache2 restart
