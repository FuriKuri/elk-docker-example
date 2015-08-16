FROM logstash

ADD conf/01-lumberjack-input.conf /conf/01-lumberjack-input.conf
ADD conf/10-json.conf /conf/10-json.conf
ADD conf/30-jsonlog.conf /conf/30-jsonlog.conf

ADD conf/logstash-forwarder.crt /pki/logstash-forwarder.crt
ADD conf/logstash-forwarder.key /pki/logstash-forwarder.key
