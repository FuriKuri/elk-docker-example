# elk-docker-example

## Generate SSL Certificates 
```shell
openssl req -config openssl.cnf -x509 -days 3650 -batch -nodes -newkey rsa:2048 -keyout logstash-forwarder.key -out logstash-forwarder.crt
```

```shell
openssl req -subj '/CN=logstash_server_fqdn/' -x509 -days 3650 -batch -nodes -newkey rsa:2048 -keyout logstash-forwarder.key -out logstash-forwarder.crt
```

