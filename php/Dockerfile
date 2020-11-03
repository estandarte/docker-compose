FROM php:fpm
RUN \
  apt-get -o Acquire::Check-Valid-Until=false -o Acquire::Check-Date=false update && \
  apt-get install -y \
  curl \
  wget \
  git

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng-dev \
        libicu-dev \
        libicu63  \
#    && docker-php-ext-install exif \
#    && docker-php-ext-install mbstring \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-install mysqli \
    && docker-php-ext-install pdo \
#    && docker-php-ext-install intl \
#    && docker-php-ext-install opcache \
    && docker-php-ext-install gd 
#    && docker-php-ext-install zip

#COPY php.ini        /usr/local/etc/php/conf.d/
COPY default.conf    /usr/local/etc/php-fpm.d/www.conf
COPY xdebug.ini    /usr/local/etc/php/conf.d/xdebug.ini

RUN pecl install xdebug;
#     echo -e '\n\n[XDEBUG]\nzend_extension="/usr/lib64/php/modules/xdebug.so"' >> /etc/php.d/xdebug.ini; \
#     echo "error_reporting=E_ALL" >> /etc/php.d/xdebug.ini; \
#     echo "display_startup_errors=On" >> /etc/php.d/xdebug.ini; \
#     echo "display_errors=On" >> /etc/php.d/xdebug.ini; \
#     echo "xdebug.remote_enable=1" >> /etc/php.d/xdebug.ini; \
#     echo "xdebug.remote_host=192.168.1.109" >> /etc/php.d/xdebug.ini; \
#     echo "xdebug.remote_port=9000" >> /etc/php.d/xdebug.ini; \
#     echo "xdebug.remote_handler=dbgp" >> /etc/php.d/xdebug.ini; \
#     echo "xdebug.remote_autostart=1" >> /etc/php.d/xdebug.ini; \
#     echo "xdebug.remote_connect_back=0" >> /etc/php.d/xdebug.ini; \
#     echo "xdebug.idekey=docker" >> /etc/php.d/xdebug.ini; 

EXPOSE 9000

#    && docker-php-ext-install iconv \
#    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
#    && docker-php-ext-install gd \
