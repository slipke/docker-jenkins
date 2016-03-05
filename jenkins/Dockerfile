FROM jenkins

USER root

# Install ant
RUN apt-get update \
    && apt-get install -y ant php5

# Install composer
RUN php -r "readfile('https://getcomposer.org/installer');" > composer-setup.php \
    && php composer-setup.php --install-dir=/usr/local/bin --filename=composer \
    && php -r "unlink('composer-setup.php');"

USER jenkins

COPY jenkins/php-template/config.xml /usr/share/jenkins/ref/jobs/php-template/
COPY jenkins/plugins.txt /usr/share/jenkins/ref/

RUN /usr/local/bin/plugins.sh /usr/share/jenkins/ref/plugins.txt