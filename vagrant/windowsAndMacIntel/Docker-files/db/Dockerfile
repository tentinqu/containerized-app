FROM mysql:8.0.33
LABEL "Project"="vprofile-project"
LABEL "Version"="1.0"

ENV MYSQL_ROOT_PASSWORD="root"
ENV MYSQL_DATABASE="accounts"
ENV MYSQL_USER=vprofile_user    

ADD db_backup.sql docker-entrypoint-initdb.d/db_backup.sql
# This Dockerfile sets up a MySQL database for the vprofile project.