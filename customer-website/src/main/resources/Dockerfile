FROM 100.125.0.198:20202/hwcse/dockerhub-java:8-jre-alpine
RUN mkdir -p /home/apps/server
ADD https://100.125.0.198:20202/swr/v2/domains/servicestage/namespaces/servicestage/repositories/HouseApp/packages/tomcat/versions/8.5.24/file_paths/apache-tomcat-8.5.24.tar.gz /home/apps/server
RUN tar zxf /home/apps/server/apache-tomcat-8.5.24.tar.gz -C /home/apps/server
COPY ./customer-website/target/customer-website-0.0.1-SNAPSHOT.war /home/apps/server/apache-tomcat-8.5.24/webapps/
COPY ./customer-website/target/server.xml /home/apps/server/apache-tomcat-8.5.24/conf
RUN rm -rf /home/apps/server/apache-tomcat-8.5.24/webapps/ROOT /home/apps/server/apache-tomcat-8.5.24/webapps/docs /home/apps/server/apache-tomcat-8.5.24/webapps/examples /home/apps/server/apache-tomcat-8.5.24/webapps/host-manager /home/apps/server/apache-tomcat-8.5.24/webapps/manager 
RUN ["chmod", "+x", "/home/apps/server/apache-tomcat-8.5.24/bin/catalina.sh"]
CMD ["/home/apps/server/apache-tomcat-8.5.24/bin/catalina.sh","run"]