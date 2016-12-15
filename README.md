# Requirements

- [Docker](https://docs.docker.com/engine/installation/linux/ubuntulinux/)
- [Docker-Compose](https://docs.docker.com/compose/install/)

or simply **[launch this demo instantly on CloudShare](http://cloudshare.com/pricing-packages?envTemplate=BPXBNeZSSjSVAUtplVuB3XAA2&_ga=1.22155320.2011026143.1478775085)**

# Running

```
git clone https://github.com/cloudshare/elk.git
cd elk
docker-compose build
docker-compose -p chat up
```

# What's in the box

```
┌──────────┐  ┌──────────┐
│  Kibana  │  │ LogStash │
│ (docker) │  │ (docker) │
└──────────┘  └──────────┘
      │             │     
Search Query      Logs    
      └──────┬──────┘     
             │            
             ▼            
     ┌───────────────┐    
     │ ElasticSearch │    
     │   (docker)    │    
     └───────────────┘    
```
## LogStash

LogStash is configured to listen for FileBeat traffic on port 5044 (see `logstash/logstash.conf`).

It unpacks the inner JSON log message created by Bunyan.

Finally, it outputs logs into ElasticSearch (on port 9200 locally).

## ElasticSearch

Accepts log records for indexing on port 9200. It runs on the same network as LogStash (called `backend`) so LogStash discovers it by its hostname `es`. See `docker-compose.yml`.

## Kibana

Kibana's UI is accessible via HTTP on port 5601.
