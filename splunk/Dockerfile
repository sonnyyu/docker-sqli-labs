FROM splunk/splunk:latest
USER root
LABEL maintainer "sonnyyuirm@gmail.com"
RUN  mkdir -p /var/log/apache2 \
  && mkdir -p /var/log/mysql 
RUN ln -fs /usr/share/zoneinfo/America/Los_Angeles /etc/localtime
RUN dpkg-reconfigure -f noninteractive tzdata
RUN touch /var/log/apache2/access.log \
  && touch /var/log/mysql/all.log 
RUN chmod 777 -R /var/log/apache2 \
  && chmod 777 -R /var/log/mysql 
ADD SQL_Injection.tgz  /opt/splunk/etc/apps
RUN chmod 755 -R /opt/splunk/etc/apps/SQL_Injection
RUN chown splunk:splunk -R /opt/splunk/etc/apps/SQL_Injection