############################################################
# Dockerfile to build CentOS,Python installed  Container
# Based on CentOS
############################################################

# Set the base image to Ubuntu
FROM centos:latest

# File Author / Maintainer
MAINTAINER xinfeng <flychen50@gmail.com>

#RUN yum install -y emacs
# Installing supervisor
RUN yum -y install python-{pip,zmq,jinja2} numpy scipy pandoc
RUN yum -y install gcc-c++ freetype-devel libpng-devel atlas-devel blas-devel


ENV PIP_CONF_DIR /root/.pip
ADD http://7xj2r6.com1.z0.glb.clouddn.com/pip-7.1.0.tar.gz  /root/
RUN cd /root && tar -zxvf pip-7.1.0.tar.gz&& cd pip-7.1.0 && python setup.py install
RUN mkdir -p ${PIP_CONF_DIR}
ADD pip.conf ${PIP_CONF_DIR}/pip.conf
RUN pip install matplotlib
RUN pip install requests
RUN pip install mysql-connector-python --allow-external mysql-connector-python
