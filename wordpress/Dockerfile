FROM centos:latest 
MAINTAINER remo at mattei dot org
RUN yum -y update; yum clean all

RUN yum -y install httpd php php-mysql php-gd openssl psmisc tar 
RUN yum clean all

ADD scripts /scripts
RUN curl -LO http://wordpress.org/latest.tar.gz                   
RUN tar xvzf /latest.tar.gz -C /var/www/html --strip-components=1  
RUN rm /latest.tar.gz                                             
RUN chown -R apache:apache /var/www/
RUN chmod 755 /scripts/*

EXPOSE 80
CMD ["/bin/bash", "/scripts/start.sh"]
