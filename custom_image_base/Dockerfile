FROM registry.redhat.io/rhel8/httpd-24
USER 0
# Add application sources
ADD https://raw.githubusercontent.com/hoffoh/openshift-httpd/main/index_base/index.html /var/www/html/index.html
RUN chmod -R 666 /var
# The run script uses standard ways to run the application
CMD run-httpd
