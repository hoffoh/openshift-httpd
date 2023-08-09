FROM registry.redhat.io/rhel8/httpd-24
USER 0
# Add application sources
# The run script uses standard ways to run the application
ADD https://raw.githubusercontent.com/hoffoh/openshift-httpd/main/index/index.html /var/www/html/index.html
ADD  https://github.com/hoffoh/openshift-httpd/blob/main/images/wp.jpg?raw=true /var/www/html/wp.jpg
RUN chown -R root:apache /var/www && chmod 644 /var/www/html/index.html && chmod 644 /var/www/html/wp.jpg 
CMD run-httpd
