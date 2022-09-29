FROM docker.elastic.co/beats/filebeat:7.9.2

COPY filebeat.yml /usr/share/filebeat/filebeat.yml

USER root
RUN chown root:filebeat /usr/share/filebeat/filebeat.yml

USER filebeat
