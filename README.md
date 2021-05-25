# FireELK 🔥🦌
An ELK stack used for processing and visualizing firewall logs

v.04

![Firewall Logs](https://github.com/maxabaumgarten/fireelk/blob/master/images/firewall%20logs.PNG)
![Cool Pew Pew Map](https://github.com/maxabaumgarten/fireelk/blob/master/images/firewall%20laser%20beam%20map.PNG)
![ELK Firewall Charts](https://github.com/maxabaumgarten/fireelk/blob/master/images/elk%20firewall%20visualization.PNG)
# WARNING
- The passwords are all in plaintext
- Look at the code, the passwords are all "Letmein123!"
- Certificate based authentication/encryption coming soon

# Details
- Provides a unified platform to ingest, parse, and visualize firewall logs
- Centralize multi-vendor logs
- Converts firewall syslog into the ECS (Elastic Common Schema) with Logstash
- Docker-Compose: Spins up a single node cluster of Elasticsearch, Logstash, Kibana
- Password Based X-Pack Security (The password is Letmein123!)

# Who should use this?
- Homelabbers who want a simple functioning ELK stack
- Enterprises looking to test out the ELK stack
- Enterprises looking to not pay by the GB for fancy SIEMs (Bad idea)
- Employees who want to show upper management cool dashboards during their performance review

# How do I run this?
1. Install Docker and Docker-Compose
2. Create the following folders/files:

- ./elasticsearch/elasticsearch.yml
- ./logstash/config/logstash.yml
- ./logstash/pipeline (Pipelines are used for the logstash configs)
- ./kibana/kibana.yml
(.yml files not available yet. Visit www.elastic.co to get started)

3.  docker-compose up -d

# Supported Firewall Syslog ECS Conversions
- Check Point (Gaia Embedded)
- Fortinet
- Check Point (Gaia) - BETA

# Planned Features

- NGFW Feature ECS Conversion (IPS, AV, Emulation, Filtering, DNS Security)
- Palo Alto Syslog > ECS
- Cisco Syslog > ECS
- VyOS/Ubiquiti Edgerouter Syslog > ECS
- Certificate Based X-Pack Security
- Improved Elastic Security (SIEM) support
- Use .env file for credentials