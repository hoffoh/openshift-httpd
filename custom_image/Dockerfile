# This is a comment line
FROM registry.access.redhat.com/ubi8/ubi:8.0 
LABEL description="This is a custom httpd container image"
MAINTAINER HoffoH hoffoh@home.is
RUN yum install -y httpd
USER 1001
CMD bash -c "sleep 50000"
