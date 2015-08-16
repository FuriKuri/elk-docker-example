# elk-docker-example

## Start
```shell
cd elk-server
docker-compose up
```

```shell
cd elk-client
docker-compose up
```

## Generate SSL Certificates

Copy logstash-forwarder.key to elk-server/logstash/conf.
Copy logstash-forwarder.crt to elk-server/logstash/conf and elk-client/logstash-forwarder/conf.
Change IP/FQDN in elk-client/logstash-forwarder/conf/logstash-forwarder.conf.

### IP Address
Change IP address in [ v3_ca ] section in elk-server/openssl.cnf file.
```shell
openssl req -config openssl.cnf -x509 -days 3650 -batch -nodes -newkey rsa:2048 -keyout logstash-forwarder.key -out logstash-forwarder.crt
```

### FQDN (DNS)
```shell
openssl req -subj '/CN=logstash_server_fqdn/' -x509 -days 3650 -batch -nodes -newkey rsa:2048 -keyout logstash-forwarder.key -out logstash-forwarder.crt
```



