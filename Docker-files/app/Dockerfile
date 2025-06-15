FROM maven:3.9.9-eclipse-temurin-21-jammy AS build
RUN git clone https://github.com/hkhcoder/vprofile-project.git
RUN cd vprofile-project && git checkout containers && mvn install


FROM tomcat:10.1.27-jdk21
LABEL "Project"="vprofile-project"
LABEL "Version"="1.0"
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=build /vprofile-project/target/vprofile.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]
# This Dockerfile builds a Java application using Maven and deploys it to a Tomcat server.