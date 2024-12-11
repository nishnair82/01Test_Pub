FROM tomcat:8.5-alpine

# Deploy the superveda app into the webapps folder.
# We have to wipe out the existing default apps first
RUN rm -rf /usr/local/tomcat/webapps/
COPY ./superveda.war /usr/local/tomcat/webapps/ROOT.war
