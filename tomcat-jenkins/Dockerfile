FROM ubuntu:20.04

WORKDIR /opt/tomcat

RUN apt-get -y update && apt-get -y upgrade
# Install jdk
RUN apt-get -y install openjdk-11-jdk wget
# Install curl to get the tomcat file zipped
RUN apt-get -y install curl
RUN mkdir /usr/local/tomcat
RUN cd /usr/local/tomcat
# Option (-O) The documents will not be written to the appropriate files, but all will be concatenated together and written to file.
RUN wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.70/bin/apache-tomcat-9.0.70.tar.gz -O tomcat.tar.gz
# Unzipped files
RUN tar xvfz tomcat.tar.gz
RUN cp -Rv apache-tomcat-9.0.70/* /usr/local/tomcat/

EXPOSE 8080


ENV JAVA_HOME /usr/lib/jvm/java-11-openjdk-amd64

COPY jenkins.war /usr/local/tomcat/webapps

WORKDIR /usr/local/tomcat/webapps

# CMD ["/usr/local/tomcat/bin/startup.sh", "run"]

# CMD ["/usr/local/tomcat/bin/catalina.sh" "run"]
# "/usr/local/tomcat/bin/startup.sh"

CMD ["bash"]