FROM registry.redhat.io/rhel8/httpd-24

# Add application sources
ADD https://raw.githubusercontent.com/hoffoh/openshift-httpd/main/index/index.html /tmp/src/index.html
ADD  https://github.com/hoffoh/openshift-httpd/blob/main/images/wp.jpg?raw=true /tmp/src
RUN chmod -R 666 /tmp/src
# The run script uses standard ways to run the application
CMD run-httpd
