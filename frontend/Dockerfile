#list of commands in docker:
#FROM image
#MAINTAINER
#RUN
#ADD
#COPY
#ENV
#EXPOSE
#CMD
#ENTRYPOINT
#USER
#WORKDIR
#VOLUME
#ARG

FROM centos:7
MAINTAINER ggganeshbe@gmail.com

#Update all the existing package: yum -y update
RUN yum -y update

#Install platform : yum -y install httpd
RUN yum -y install httpd

#switch user
#RUN useradd apache
#USER apache

RUN mkdir /apps

#After this command all the commands will be running in /apps folder
WORKDIR /apps
#VOLUME /apps

# Copy the vode to document :/ var/www/html
# ADD: code/code.zip /var/www/html -> This will extract the code and copy
# COPY: code/code.zip /var/www/html -> This will copy the zip as such ( It works with files and folders ) -> similar to cp
ADD code /var/www/html
COPY code /var/www/html

# Set the environment variable for backend lb : BACKENDLB
ENV BACKENDLB=test

# Apache is running on port 80
EXPOSE 80

# Start Apache. It doesnt run at build time. It is executed during container launch.
# sh -c "command" . In general, all these commands are executed in hash format. There should be 1 process running on foreground.
# if we give like above command, "sh" will be process 1 and "apache" will be process 2
# Hence replace it with nohup or like below
# If we give ENTRYPOINT here we cant change it during the run time
CMD ["apachectl", "-D","FOREGROUND"]

#RUN THE ARG
#ADD scripts /opt
#RUN /opt/choose.sh $MY_ARG