# Dockerfile for Ubuntu Jenkins Server
# Created by: Eamonn Buss
# Created on: 06/26/2015
# Purpose: A docker file to create a docker container for Jenkins Server

##--------------------------------------
## Start with jenkins as the base
##--------------------------------------
FROM jenkins:latest

##--------------------------------------
## Maintainer - Eamonn Buss
##--------------------------------------
MAINTAINER Eamonn Buss <eamonn@srcdevbin.com>

##--------------------------------------
## Create the jenkins user, overriding the default
##--------------------------------------
USER root
RUN deluser jenkins --quiet

##--------------------------------------
## Override the group ID to match the HOST's Group ID
##--------------------------------------
RUN groupadd jenkins -g 1002\
  && useradd -u 1001 -g jenkins -s /bin/bash jenkins


##--------------------------------------
## Set up the environment
##--------------------------------------
ENV SHELL /bin/bash
ENV JENKINS_HOME /usr/share/jenkins
WORKDIR /usr/share/jenkins
RUN ["chown", "jenkins:jenkins", "-R", "/usr/share/jenkins"]
USER jenkins

##--------------------------------------
## Start the application
##--------------------------------------
ENTRYPOINT ["java", "-jar", "/usr/share/jenkins/jenkins.war"]
EXPOSE 8080
CMD [""]
