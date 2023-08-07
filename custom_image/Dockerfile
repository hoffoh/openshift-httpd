# This is a comment line
FROM registry.access.redhat.com/ubi8/ubi:8.8-1009 
LABEL description="This is a custom httpd container image"
MAINTAINER HoffoH hoffoh@home.is
RUN yum install -y httpd
ENV PORT 8080
RUN sed -ri -e "/^Listen 80/c\Listen ${PORT}" /etc/httpd/conf/httpd.conf && \
chown -R apache:apache /etc/httpd/logs/ && \
chown -R apache:apache /run/httpd/
EXPOSE ${PORT}
ENV LogLevel "info"
ADD  https://github.com/hoffoh/openshift-httpd/blob/main/images/wp.jpg?raw=true /var/www/html/
ADD https://raw.githubusercontent.com/hoffoh/openshift-httpd/main/index/index.html /var/www/html/
RUN chown apache:apache /var/www/html/wp.jpg
RUN chown apache:apache /var/www/html/index.html
USER apache
ENTRYPOINT ["/usr/sbin/httpd"]
CMD ["-D", "FOREGROUND"]
