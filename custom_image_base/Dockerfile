FROM registry.redhat.io/rhel8/httpd-24
USER 0
# Add application sources
# The run script uses standard ways to run the application
ADD https://raw.githubusercontent.com/hoffoh/openshift-httpd/main/index/index.html /usr/share/testpage/index.html
RUN chmod 644 /usr/share/testpage/index.html
ADD  https://github.com/hoffoh/openshift-httpd/blob/main/images/wp.jpg?raw=true /usr/share/testpage/wp.jpg
RUN chmod 644 /usr/share/testpage/wp.jpg
CMD run-httpd
