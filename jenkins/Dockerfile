FROM jenkins

USER root

# Install ant
RUN apt-get update \
    && apt-get install -y ant

USER jenkins

COPY jenkins/php-template/config.xml /usr/share/jenkins/ref/jobs/php-template/