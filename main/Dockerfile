FROM ubuntu:12.04
MAINTAINER Igor Telmenko <igor-telmenko@yandex.ru>

VOLUME ["/root/share", "/var/www"]

# Packages
RUN apt-get update && \
    apt-get install -y \
      apache2 \
      memcached \
      mysql-client \
      mysql-server \
      php5 \
      php5-common \
      php5-cli \
      libapache2-mod-php5 \
      libapache2-mod-php5 \
      php5-gd \
      php5-ldap \
      php5-mysql \
      php-gettext \
      php-http-request \
      php-net-socket \
      php-net-url \
      php-pear \
      php-soap \
      php5-curl \
      php5-geoip \
      php5-mcrypt \
      php5-memcache \
      php5-xdebug \
      php5-xmlrpc \
      php5-xsl \
      iputils-ping \
      mc
      
# Locales      
RUN locale-gen fr_FR.UTF-8 \
    locale-gen tr_TR.UTF-8 \     
    locale-gen de_DE.UTF-8 \ 
    locale-gen ja_JP.UTF-8 \    
    locale-gen ru_RU.UTF-8 \ 
    locale-gen en_US.UTF-8 \     
    locale-gen es_ES.UTF-8 \  
    locale-gen it_IT.UTF-8 \
    locale-gen pl_PL.UTF-8 \
    locale-gen pt_BR.UTF-8 \
    locale-gen pt_PT.UTF-8 \
      
      
# Default host
COPY apache_default /etc/apache2/sites-available/default
# Our virtual hosts settings
COPY sites/*.conf /etc/apache2/sites-enabled/
# Another configs
COPY xdebug.ini /root/xdebug.ini
# File for CMD in the end
COPY run /usr/local/bin/run
RUN chmod +x /usr/local/bin/run
# mod_rewrite
RUN a2enmod rewrite
# mod_version
RUN a2enmod version

EXPOSE 80
CMD ["/usr/local/bin/run"]
