FROM ubuntu:latest

COPY sources.list /etc/apt/sources.list
RUN apt-get update \
 && apt-get install -y apache2 libapache2-mod-fastcgi
RUN a2enmod actions

ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2
ENV APACHE_CONFDIR /etc/apache2
ENV APACHE_LOCK_DIR /var/lock/apache2
ENV APACHE_PID_FILE /var/run/apache2/apache2.pid

EXPOSE 80
EXPOSE 443

CMD ["/usr/sbin/apache2", "-D", "FOREGROUND"]

