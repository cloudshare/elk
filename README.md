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

