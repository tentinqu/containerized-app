# ---------- Stage 1: Build the WAR using Maven ----------
FROM maven:3.9.9-eclipse-temurin-21-jammy AS build

# Set working directory
WORKDIR /app

# Clone the repo and build the project
RUN git clone https://github.com/hkhcoder/vprofile-project.git

WORKDIR /app/vprofile-project

RUN git checkout containers && mvn clean install

# ---------- Stage 2: Deploy to Tomcat ----------
FROM tomcat:10-jdk17-temurin


LABEL "Project"="vprofile-project"
LABEL "Version"="1.0"

# Clean default webapps
RUN rm -rf /usr/local/tomcat/webapps/*

# Copy the built WAR file
COPY --from=build /app/vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

# Expose the default Tomcat port
EXPOSE 8080

# Start Tomcat
CMD ["catalina.sh", "run"]
