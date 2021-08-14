FROM tomcat:9.0

# restore the manager and root Tomcat apps for testing
RUN mv /usr/local/tomcat/webapps /usr/local/tomcat/webapps.old && \
    mv /usr/local/tomcat/webapps.dist /usr/local/tomcat/webapps

# add a custom tomcat-users.xml file to enable manager GUI users
COPY tomcat-users.xml /usr/local/tomcat/conf/tomcat-users.xml

# add a custom manager.xml context to allow access to manager apps
COPY manager.xml /usr/local/tomcat/conf/Catalina/localhost/manager.xml