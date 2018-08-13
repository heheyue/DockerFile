FROM centos6.6:0.0.1

MAINTAINER syberos:yanxinyue

RUN mv /etc/yum.repos.d/ /etc/yum.repos.d_bak/ && mkdir /etc/yum.repos.d

ADD 102.repo /etc/yum.repos.d

RUN yum clean all && yum install -y mysql-server mysql-devel mysql && /etc/init.d/mysqld start  && mysqladmin -u root password 123456 && mysql -u root -p123456 -e "Grant all privileges on *.* to 'root'@'%' identified by '123456' with grant option;" 
#mysql -u root -p123456 -e "DROP DATABASE test;" && mysql -u root -p123456 -e "drop user root@'localhost.localdomain'" &&  mysql -u root -p123456 -e "drop user root@'127.0.0.1'" && mysql -u root -p123456 -e "drop user root@'::1'" && mysql -u root -p123456 -e "DELETE FROM mysql.user WHERE Host='localhost' and User = '';" && mysql -u root -p123456 -e "DELETE FROM mysql.user WHERE Host='localhost.localhostdomain' and User = '';"

RUN sed -i 's@user=mysql@user=root@' /etc/my.cnf

#RUN /etc/init.d/httpd start

EXPOSE 3306

CMD /usr/bin/mysqld_safe
