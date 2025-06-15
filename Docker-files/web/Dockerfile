FROM nginx
LABEL "Project"="vprofile-project"
LABEL "Version"="1.0"

RUN rm -rf /etc/nginx/conf.d/default.conf
COPY nginvpropapp.conf /etc/nginx/conf.d/vproapp.conf