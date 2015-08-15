# Set the base image to Ubuntu
FROM centos:6

# File Author / Maintainer
MAINTAINER dongying <26375011@qq.com>
#RUN /bin/rpm -ivh http://ftp.uninett.no/linux/epel/6/i386/epel-release-6-8.noarch.rpm
#RUN /bin/rpm -ivh http://rpms.famillecollet.com/enterprise/remi-release-6.rpm
#centos6 default php5.4
RUN yum -y --enablerepo=remi,remi-php53 install php-fpm php-common
# get pear (https://pear.php.net/)
# RUN curl -Ls -o /usr/local/bin/go-pear.phar https://pear.php.net/go-pear.phar && \
# chmod 755 /usr/local/bin/go-pear.phar && \
# ln -s /usr/local/bin/go-pear.phar /usr/local/bin/go-pear
RUN yum -y install php-pear
RUN yum -y install php-devel
RUN yum -y install gcc zlib zlib-devel  memcached cyrus-sasl cyrus-sasl-devel
RUN yum -y install libmemcached libmemcached-devel
# RUN pecl install -o -f redis \
# &&echo "extension=redis.so" > /etc/php.d/redis.ini
# RUN pecl install -o -f memcache \
# &&echo "extension=memcache.so" > /etc/php.d/memcache.ini
# RUN pecl install -o -f memcached \
# &&echo "extension=memcached.so" > /etc/php.d/memcached.ini
RUN /bin/rpm -ivh http://ftp.uninett.no/linux/epel/6/i386/epel-release-6-8.noarch.rpm
RUN /bin/rpm -ivh http://rpms.famillecollet.com/enterprise/remi-release-6.rpm
RUN yum --enablerepo=remi,remi-php53 install -y php-pecl-memcached.x86_64
RUN yum --enablerepo=remi,remi-php53 install -y php-pecl-memcache.x86_64
RUN yum --enablerepo=remi,remi-php53 install -y php-pecl-redis.x86_64
RUN sed -ri 's/;date.timezone =/date.timezone = Asia\/Shanghai/g' /etc/php.ini
RUN rm /etc/localtime \
&& ln -s /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
