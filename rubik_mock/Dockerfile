FROM r.biz.weibo.com:443/rubik_goods:0.6
MAINTAINER xinfeng@staff.weibo.com
RUN rpm -ivh http://10.210.208.36/rpms-ad/feed-test/pbserializer-1.0.0-0.x86_64.rpm
RUN rpm -ivh http://10.210.208.36/rpms-ad/feed-test/rubik_mock-1.0.0-0.x86_64.rpm
RUN /sbin/ldconfig
ADD mock_goods.sh /home/w/share/rubik_mock/mock_goods.sh
RUN chmod +x /home/w/share/rubik_mock/mock_goods.sh

ENTRYPOINT ["/home/w/share/rubik_mock/mock_goods.sh"]
#CMD ["/home/w/share/rubik_mock/mock_goods.sh"]
