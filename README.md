# FireELK 🔥🦌

* v1.0

An ELK Stack deployed with TLS Security for Logs

- Two docker-compose commands and you have a fully functioning ELK stack.
- Set credentials/details with ```.env``` file
- Provides a unified platform to ingest, parse, and visualize log

![Firewall Logs](https://github.com/maxabaumgarten/fireelk/blob/master/images/firewall%20logs.PNG)
![Cool Pew Pew Map](https://github.com/maxabaumgarten/fireelk/blob/master/images/firewall%20laser%20beam%20map.PNG)
![ELK Firewall Charts](https://github.com/maxabaumgarten/fireelk/blob/master/images/elk%20firewall%20visualization.PNG)

## WARNING

- Passwords are set using the .env.  Default password is "Letmein123!"
- This was built in mind for simple functionality. Not Security.
- Tested with ELK 7.11, 7.12, and 7.13.0 on Ubuntu 20.04 and Docker-Compose 3.7

## Details

This was built with a focus on Network Security logging, analysis, and alerting, but can be used for any other log analysis.  Currently, this is ships with a Logstash Pipeline for analyzing Check Point and Fortinet logs and processing them into the ECS.

Here is the basic topology of how I use it:

![Example Topology](https://github.com/maxabaumgarten/fireelk/blob/master/images/ELK.png)

- Check Point and Fortinet send syslog to a server which does some basic processing with rsyslog.  Filebeat is then used to tag and ship the logs to the docker host running Logstash ( Elasticsearch, and Kibana). Filebeat logs for firewalls ingest on port 5044.  Logstash converts syslog to the ECS and then Elasticsearch applies an index template.  Logs can now be visualized using Kibana and SIEM operations can be performed using Elastic Security.  Logstash Pipeline for firewalls can be found in the ```firewallpipe.conf``` file.
- PiHole DNS logs now have a pipeline (Added 6/2/2021).  I run a Filebeat container and send the logs to Logstash on port 5045. Logstash Pipeline for PiHole can be found in the ```piholepipe.conf``` file.

*This is just my setup and how I use it.  This is a fully functional ELK stack right out of the box and you can simply ingest logs in one of the myriads of ways ELK provides.*

## Who should use this?

- Homelabbers who want a simple functioning ELK stack
- Enterprises looking to test out the ELK stack
- Enterprises looking to not pay by the GB for fancy SIEMs (Bad idea)
- Employees who want to show upper management cool dashboards during their performance review

## How do I run this?

1. Install Docker and Docker-Compose
2. Clone Repo
```sh
git clone https://github.com/maxabaumgarten/FireELK.git
```
3. Create CA and Certificates
```sh
docker-compose -f create-certs.yml run --rm create_certs
```
4. Build and Start ELK
```sh
docker-compose up -d
```
5. Login to Kibana @ *https://your-docker-server:5601*
   - User: elastic
   - Password: *Default:* Letmein123! (*Or whatever is set in ```.env``` file*)

## How do I destroy this?

This will destroy all of your data.
```sh
docker-compose down -v
```

## Built-In ECS Conversions

- Check Point (Gaia Embedded) - ```firewallpipe.conf```
- Fortinet - ```firewallpipe.conf```
- Check Point (Gaia) - BETA - ```firewallpipe.conf```
- PiHole - ```piholepipe.conf``` 

## Planned Features

- NGFW Feature ECS Conversion (IPS, AV, Emulation, Filtering, DNS Security)
- Palo Alto Syslog > ECS
- Cisco Syslog > ECS
- VyOS/Ubiquiti Edgerouter Syslog > ECS
