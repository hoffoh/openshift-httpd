# This is a comment line
FROM registry.access.redhat.com/ubi8/ubi:8.8-1009 
USER 1001
LABEL description="This is a custom httpd container image"
MAINTAINER HoffoH hoffoh@home.is
RUN yum install -y httpd
ENV PORT 8080
RUN sed -ri -e "/^Listen 80/c\Listen ${PORT}" /etc/httpd/conf/httpd.conf && \
chown -R apache:apache /etc/httpd/logs/ && \
chown -R apache:apache /run/httpd/
EXPOSE ${PORT}
ENV LogLevel "info"
ENTRYPOINT ["/usr/sbin/httpd"]
CMD ["-D", "FOREGROUND"]
