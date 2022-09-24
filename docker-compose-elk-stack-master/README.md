# Dockers-ELK

Run the latest version of the ELK (Elasticsearch, Logstash, Kibana) stack with Docker and Docker Compose.

It will give you the ability to analyze any data set by using the searching/aggregation capabilities of Elasticsearch
and the visualization power of Kibana.

Based on the official Docker images:

* [elasticsearch](https://github.com/elastic/elasticsearch-docker)
* [logstash](https://github.com/elastic/logstash-docker)
* [kibana](https://github.com/elastic/kibana-docker)

# How to setup 

1. Clone this repository
2. Start the ELK stack using `docker-compose`:
```console
$ docker-compose up
```
# OR
You can also choose to run it in background (detached mode):
```console
$ docker-compose up -d
```
3. Test using sample log files 
```console
wget https://download.elastic.co/demos/kibana/gettingstarted/logs.jsonl.gz
gunzip logs.jsonl.gz
cat logs.jsonl | nc localhost 5000
```

Give Kibana a few seconds to initialize, then access the Kibana web UI by hitting
[http://localhost:5600](http://localhost:5600)
[http://localhost:5601](http://localhost:5601)
[http://localhost:5602](http://localhost:5602)
[http://localhost:5603](http://localhost:5603)

By default, the stack exposes the following ports:
* 5000: Logstash TCP input.
* 9200: Elasticsearch HTTP
* 9300: Elasticsearch TCP transport
* 5600-3: Kibana Ports
