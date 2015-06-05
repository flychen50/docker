FROM r.biz.weibo.com:443/centos5
MAINTAINER xinfeng@staff.weibo.com
RUN yum install -y rpm*
RUN yum install -y gcc*
RUN yum install -y subversion
RUN yum install -y wget
RUN yum install -y curl*
RUN yum install -y make.x86_64
RUN yum install -y ncurses.x86_64
RUN yum install -y ncurses-devel.x86_64
RUN yum install -y emacs
#RUN yum install -y supervisor
ADD rsyncd.conf /etc/rsyncd.conf
COPY scripts /scripts
RUN chmod +x /scripts/install
RUN chmod +x /scripts/start
RUN /scripts/install

#RUN mkdir -p /var/run/sshd
#RUN mkdir -p /var/log/supervisor
#COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 9955 9999

#VOLUME ["/data0/vad/rubik/"]
ENTRYPOINT ["/scripts/start"]
#CMD ["/usr/bin/supervisord"]
