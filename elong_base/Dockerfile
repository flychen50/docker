############################################################
# Dockerfile to build CentOS,Python installed  Container
# Based on CentOS
############################################################

# Set the base image to Ubuntu
FROM  centos 
#FROM gpmidi/centos-6.4

# File Author / Maintainer
MAINTAINER xinfeng <flychen50@gmail.com>


# # Change to 163 yum repo
# RUN yum -y install wget tar
# #RUN echo "Change to 163 repo"
# RUN wget http://mirrors.163.com/.help/CentOS6-Base-163.repo
# RUN mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.bak
# RUN mv CentOS6-Base-163.repo /etc/yum.repos.d/CentOS-Base.repo

# #RUN wget http://mirrors.sohu.com/help/CentOS-Base-sohu.repo
# #RUN mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.bak
# #RUN mv CentOS-Base-sohu.repo /etc/yum.repos.d/CentOS-Base.repo

# RUN echo "Repo changed"
# RUN yum clean all
# RUN yum makecache
# RUN yum update -y
# RUN echo "yum updated to 163 repo"

#RUN yum install -y emacs
# Installing supervisor
RUN yum -y install python-{pip,zmq,jinja2}
RUN yum -y install gcc-c++ freetype-devel make cmake clang
RUN yum -y install emacs
RUN yum -y install svn
RUN yum -y install openssl openssl-devel tbb tbb-devel
# ADD http://mirrors.ustc.edu.cn/gnu/emacs/emacs-24.5.tar.gz  /root/
RUN yum -y install tar
RUN yum -y install ncurses-devel
RUN yum -y install git autoconf automake libtool curl
# RUN cd /root && tar -zxvf emacs-24.5.tar.gz && cd emacs-24.5 && ./configure && make && make install
# ADD emacs.d.tar.gz /root
# ADD cask.tar.gz /root
