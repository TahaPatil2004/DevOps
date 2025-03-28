FROM ubuntu:22.04


RUN apt update -y && \
    apt install -y unzip default-jre 
RUN apt-get clean 
ADD https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.100/bin/apache-tomcat-9.0.100.zip /opt
RUN unzip /opt/apache-tomcat-9.0.100.zip -d /opt

WORKDIR /opt/apache-tomcat-9.0.100/

ADD  https://s3-us-west-2.amazonaws.com/studentapi-cit/student.war /opt/apache-tomcat-9.0.100/webapps/
ADD  https://s3-us-west-2.amazonaws.com/studentapi-cit/mysql-connector.jar /opt/apache-tomcat-9.0.100/lib/
COPY context.xml /opt/apache-tomcat-9.0.100/conf/context.xml

RUN chmod +rwx /opt/apache-tomcat-9.0.100/bin/*.sh

CMD ["/opt/apache-tomcat-9.0.100/bin/catalina.sh", "run"]

EXPOSE 8080
    
    