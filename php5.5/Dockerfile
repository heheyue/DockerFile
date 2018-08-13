FROM centos6.6:0.0.3

MAINTAINER syberos:yanxinyue

RUN mv /etc/yum.repos.d/ /etc/yum.repos.d_bak/ && mkdir /etc/yum.repos.d

ADD 102.repo /etc/yum.repos.d

RUN yum clean all && yum install -y php55w*

EXPOSE 80

CMD /usr/sbin/httpd -D FOREGROUND
