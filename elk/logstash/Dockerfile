FROM docker.elastic.co/logstash/logstash:7.9.2

RUN rm -f /usr/share/logstash/pipeline/logstash.conf

ADD logstash.conf /usr/share/logstash/pipeline/logstash.conf
