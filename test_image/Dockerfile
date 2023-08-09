FROM registry.redhat.io/rhel8/httpd-24

# Add application sources
ADD https://raw.githubusercontent.com/hoffoh/openshift-httpd/main/index/index.html /var/www/html/index.html

# The run script uses standard ways to run the application
CMD run-httpd
