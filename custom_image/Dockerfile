# This is a comment line
FROM registry.access.redhat.com/ubi8/ubi:8.0 
LABEL description="This is a custom httpd container image"
MAINTAINER HoffoH hoffoh@home.is
RUN yum install -y httpd
ENV PORT 8080
RUN sed -ri -e "/^Listen 80/c\Listen ${PORT}" /etc/httpd/conf/httpd.conf && \
EXPOSE ${PORT}
ENV LogLevel "info"
ADD  https://github.com/hoffoh/openshift-httpd/blob/main/images/wp.jpg?raw=true /var/www/html/
ADD https://raw.githubusercontent.com/hoffoh/openshift-httpd/main/index/index.html /var/www/html/
RUN chown 1001:1001 /var/www/html/wp.jpg
RUN chown 1001:1001 /var/www/html/index.html
USER 1001
ENTRYPOINT ["/usr/sbin/httpd"]
CMD ["-D", "FOREGROUND"]
