FROM centos6.6:0.0.1
MAINTAINER syberos:yanxinyue
#设置时区
RUN /bin/cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo 'Asia/Shanghai' >/etc/timezone
#RUN mv /etc/yum.repos.d/ /etc/yum.repos.d_bak/ && mkdir /etc/yum.repos.d
#ADD 102.repo /etc/yum.repos.d
RUN mkdir -p /home/eimserver && mkdir -p /home/uploads/syberos_im_uploads
#ADD ./* /home/eimserver/program/
ADD ./start_im.sh /home/
#RUN mkdir -p /home/eimserver/program/log && mkdir -p /home/eimserver/program/file && mkdir -p /home/eimserver/program/icon1 && mkdir -p /home/eimserver/program/icon2 && chmod 777 -R /home/eimserver/
EXPOSE 8051/tcp
EXPOSE 8061/tcp
EXPOSE 8050/tcp
EXPOSE 8064/tcp
EXPOSE 8020/tcp
EXPOSE 12000/udp
EXPOSE 12001/udp
EXPOSE 12002/udp
EXPOSE 12003/udp
VOLUME /home/uploads/syberos_im_uploads
VOLUME /home/eimserver/program
CMD /bin/sh /home/start_im.sh
#CMD /bin/bash && tail -f tail -f /var/log/btmp
