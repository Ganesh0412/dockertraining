FROM ubuntu:18.04
MAINTAINER ggganeshbe@gmail.com

USER root
RUN apt-get -y update 

RUN apt-get -y install tzdata
ENV TZDATA=Asia/kolkata
RUN apt-get -y install nginx php php-gd php-mysql
ADD config /opt

#RUN apt-get -y install `cat /opt/nginxphp`
#RUN apt-get -y install `cat /opt/phpgenericcmod`
#RUN apt-get -y install `cat /opt/phpprojectmod`

#RUN mkdir /apps
#WORKDIR /apps

COPY code /var/www/html

EXPOSE 80

CMD ["nginx", "-g","daemon off;"]
