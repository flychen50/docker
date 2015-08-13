############################################################
# Dockerfile to build CentOS,Nginx installed  Container
# Based on CentOS
############################################################

# Set the base image to Ubuntu
FROM centos:latest

# File Author / Maintainer
MAINTAINER xinfeng <flychen50@gmail.com>

# Add the ngix and PHP dependent repository
ADD nginx.repo /etc/yum.repos.d/nginx.repo

# Installing nginx
RUN yum -y install nginx

# Installing PHP
RUN yum -y --enablerepo=remi,remi-php56 install nginx php-fpm php-common
RUN yum install -y  php-pecl-memcache
RUN yum install -y  php-mysql
RUN yum install -y python-setuptools

# Installing supervisor
ENV PIP_CONF_DIR /root/.pip
ADD http://7xj2r6.com1.z0.glb.clouddn.com/pip-7.1.0.tar.gz  /root/
RUN cd /root && tar -zxvf pip-7.1.0.tar.gz&& cd pip-7.1.0 && python setup.py install
RUN mkdir -p ${PIP_CONF_DIR}
ADD pip.conf ${PIP_CONF_DIR}/pip.conf
RUN pip install supervisor

# Adding the configuration file of the nginx
ADD nginx.conf /etc/nginx/nginx.conf
ADD default.conf /etc/nginx/conf.d/default.conf

# Adding the configuration file of the Supervisor
ADD supervisord.conf /etc/

# Adding the default file
ADD index.php /var/www/index.php


# Set up php.ini
RUN sed -ri 's/error_reporting = E_ALL & ~E_DEPRECATED & ~E_STRICT/error_reporting = E_COMPILE_ERROR|E_RECOVERABLE_ERROR|E_ERROR|E_CORE_ERROR/g' /etc/php.ini
RUN sed -ri 's/;date.timezone =/date.timezone = Asia\/Shanghai/g' /etc/php.ini
RUN rm /etc/localtime \
&& ln -s /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
# Set the port to 80
EXPOSE 80

# Executing supervisord
CMD ["supervisord", "-n"]
