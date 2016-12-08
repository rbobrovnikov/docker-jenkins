FROM selenium/node-firefox
MAINTAINER Selenium <selenium-developers@googlegroups.com>

USER root

#====================================
# Scripts to run Selenium Standalone
#====================================

COPY slave.jar /opt/selenium/slave.jar
RUN chown seluser:seluser /opt/selenium/slave.jar

ENV SE_OPTS "-role node -port 5555 -hub http://jenkins-docker.office:4444/grid/register -browser browserName=firefox,maxInstances=1"
COPY entry_point.sh /opt/bin/entry_point.sh
RUN chmod +x /opt/bin/entry_point.sh
CMD /opt/bin/entry_point.sh

USER seluser

EXPOSE 5555
