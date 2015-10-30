FROM debian:wheezy

MAINTAINER Wahyu Taufik <wahyutaufik37@gmail.com>

RUN echo "Acquire::http { Proxy \"http://192.168.1.10:3142\"; };" > /etc/apt/apt.conf.d/02proxy && \
	echo "deb http://kambing.ui.ac.id/debian/ wheezy main" > /etc/apt/sources.list && \
    echo "# deb http://kambing.ui.ac.id/debian/ wheezy-updates" >> /etc/apt/sources.list && \
    echo "deb http://kambing.ui.ac.id/debian-security/ wheezy/updates main" >> /etc/apt/sources.list && \
    apt-get update -y && \
    apt-get install -y nginx php5-fpm php5-mcrypt php5-xdebug php5-dev php-pear build-essential && \
    pecl install mongo

ADD ./php.ini /etc/php5/fpm/
ADD ./default /etc/nginx/sites-available/default
ADD ./index.php /srv/www/
#ADD ./php5-fpm.sock /var/run/

#RUN chown www-data:www-data /var/run/php5-fpm.sock

EXPOSE 80 9000

VOLUME /srv/www

CMD ["nginx", "-g", "daemon off;"]
