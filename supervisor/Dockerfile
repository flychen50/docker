FROM ubuntu:13.04
MAINTAINER examples@docker.com
RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y openssh-server  perl apache2.2-common apache2 supervisor
# apache2.2-common apache2 : Depends: apache2-mpm-worker (= 2.2.22-1ubuntu1) but it is not going to be installed or
# apache2-mpm-prefork (= 2.2.22-1ubuntu1) but it is not going to be installed or
# apache2-mpm-event (= 2.2.22-1ubuntu1) but it is not going to be installed or
# apache2-mpm-itk (= 2.2.22-1ubuntu1) but it is not going to be installed
# Depends: apache2.2-common (= 2.2.22-1ubuntu1) but it is not going to be installed

RUN mkdir -p /var/run/sshd
RUN mkdir -p /var/log/supervisor
COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf
EXPOSE 22 80
CMD ["/usr/bin/supervisord"]
