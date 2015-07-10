# dolia/nginx-php
#
# VERSION       1.0

# use the ubuntu base image provided by dotCloud
FROM richarvey/nginx-php-fpm

# enable php  mcrypt
RUN php5enmod mcrypt

# install nodejs

RUN apt-get install -y nodejs

# node link to nodejs

RUN ln -s /usr/bin/nodejs /usr/bin/node

# install npm

RUN curl -L https://npmjs.org/install.sh | sh

# install grunt 

RUN npm install -g grunt-cli

# install gulpjs

RUN npm install -g gulp

# install bower

RUN npm install -g bower


# install php composer

RUN php -r "readfile('https://getcomposer.org/installer');" | php

RUN mv composer.phar /usr/local/bin/composer


#install beantalkd

RUN apt-get -y install beanstalkd

RUN  sed -i   '$a [program:beanstalkd]\ncommand=/usr/bin/beanstalkd -l 127.0.0.1 -p 11300\nautorestart=true\nstdout_events_enabled=true\nstderr_events_enabled=true'  /etc/supervisord.conf 
