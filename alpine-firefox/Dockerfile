FROM  alpine:latest

USER root

RUN echo "http://dl-cdn.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories && \
echo "http://dl-cdn.alpinelinux.org/alpine/edge/main" >> /etc/apk/repositories
RUN apk --update --no-cache add xvfb hunspell dbus firefox
#CMD ["/usr/bin/firefox", "-no-remote"]

COPY slave.jar ~/slave.jar
CMD java -jar slave.jar -jnlpUrl http://jenkins-docker.office/computer/selenium-chrome/slave-agent.jnlp -secret be213d478eee85a6b81879f38b4b4030e00b1dcee6f95a26e4e74d50b2c60853

CMD ["Xvfb :10"]
CMD ["firefox"]
