FROM centos6.6:latest

MAINTAINER yanxinyue
#更改时区
RUN /bin/cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo 'Asia/Shanghai' >/etc/timezone

RUN rpm -Uvh http://ftp.iij.ad.jp/pub/linux/fedora/epel/6/x86_64/epel-release-6-8.noarch.rpm && rpm -Uvh http://rpms.famillecollet.com/enterprise/remi-release-6.rpm

RUN yum install -y --enablerepo=remi --enablerepo=remi-php56 php php-gd php-xml php-fpm php-ldap php-mysql php-soap php-mcrypt 

RUN sed -i 's/upload_max_filesize = 1024M/upload_max_filesize = 20M/g' /etc/php.ini 
RUN sed -i 's/;date\.timezone.*/date.timezone = "Asia\/Shanghai"  /' /etc/php.ini
RUN sed -i 's/post_max_size = 10M/post_max_size = 10M/g' /etc/php.ini
RUN sed -i 's/listen.allowed_clients = .*/;listen.allowed_clients = 127.0.0.1/g' /etc/php-fpm.d/www.conf
RUN sed -i 's/listen = .*:9000/listen = 0.0.0.0:9000/g' /etc/php-fpm.d/www.conf

EXPOSE 9000
CMD php-fpm -F
