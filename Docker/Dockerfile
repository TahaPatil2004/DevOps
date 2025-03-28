FROM ubuntu:latest 

LABEL autor="rajatz"

RUN apt update 

RUN apt install apache2 -y 

WORKDIR /var/www/html/

COPY index.html /var/www/html/index.html

EXPOSE 80

CMD ["apachectl", "-DFOREGROUND"]



FROM nginx:latest

COPY index.html /usr/share/nginx/html/index.html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]



FROM ubuntu:22.04


RUN apt update -y && \
    apt install -y unzip default-jre 
RUN apt-get clean 
ADD https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.100/bin/apache-tomcat-9.0.100.zip /opt
RUN unzip /opt/apache-tomcat-9.0.100.zip -d /opt

WORKDIR /opt/apache-tomcat-9.0.100/

ADD  https://s3-us-west-2.amazonaws.com/studentapi-cit/student.war /opt/apache-tomcat-9.0.100/webapps/
ADD  https://s3-us-west-2.amazonaws.com/studentapi-cit/mysql-connector.jar /opt/apache-tomcat-9.0.100/lib/
COPY context.xml /opt/apache-tomcat-9.0.98/conf/context.xml

RUN chmod +rwx /opt/apache-tomcat-9.0.100/bin/*.sh

CMD ["/opt/apache-tomcat-9.0.100/bin/catalina.sh", "run"]

EXPOSE 8080



# Use the official httpd image from Docker Hub
FROM httpd:latest

# Copy custom website content into the default Apache directory
COPY ./index.html/ /usr/local/apache2/htdocs/

# Expose the default Apache HTTP port
EXPOSE 80

# Start the Apache HTTP Server
CMD ["httpd-foreground"]    
    

      