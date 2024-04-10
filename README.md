FROM ubuntu:latest     
RUN apt install update -y
RUN apt install default-jdk -y
RUN apt clean
RUN wget -q https://dlcdn.apache.org/tomcat/tomcat-8/v8.5.100/bin/apache-tomcat-8.5.100.tar.gz -O /opt/
RUN tar -xvf apache-tomcat-8.5.100.tar.gz
RUN mv apache-tomcat-8.5.100.tar.gz tomcat
RUN rm /opt/apache-tomcat-8.5.100.tar.gz
RUN wget -O /opt/tomcat/webapp/ https://get.jenkins.io/war-stable/2.440.2/jenkins.war
EXPOSE 8080
