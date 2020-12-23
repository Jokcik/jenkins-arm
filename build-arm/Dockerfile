FROM jenkins4eval/jenkins
USER root

RUN apt-get update && apt-get install make
USER jenkins

# Install Plugins
COPY plugins.txt /usr/share/jenkins/ref/plugins.txt
RUN /usr/local/bin/install-plugins.sh < /usr/share/jenkins/ref/plugins.txt
