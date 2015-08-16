FROM debian:jessie

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update
RUN apt-get install -y git golang

RUN git clone git://github.com/elasticsearch/logstash-forwarder.git /tmp/logstash-forwarder
RUN cd /tmp/logstash-forwarder && git checkout v0.4.0 && go build
RUN mkdir /opt/logstash-forwarder && cp /tmp/logstash-forwarder/logstash-forwarder /opt/logstash-forwarder/logstash-forwarder

RUN rm -rf /tmp/*

ADD conf/logstash-forwarder.conf /conf/logstash-forwarder.conf
ADD conf/logstash-forwarder.crt /pki/logstash-forwarder.crt
