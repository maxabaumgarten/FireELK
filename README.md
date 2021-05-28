# FireELK 🔥🦌
An ELK Stack deployed with TLS Security for Logs

v.04

![Firewall Logs](https://github.com/maxabaumgarten/fireelk/blob/master/images/firewall%20logs.PNG)
![Cool Pew Pew Map](https://github.com/maxabaumgarten/fireelk/blob/master/images/firewall%20laser%20beam%20map.PNG)
![ELK Firewall Charts](https://github.com/maxabaumgarten/fireelk/blob/master/images/elk%20firewall%20visualization.PNG)

# WARNING

- Passwords are set using the .env
- This was built in mind for simple functionality. Not Security.
- Tested with ELK 7.11, 7.12, and 7.13.0 on Ubuntu 20.04

# Details
- Provides a unified platform to ingest, parse, and visualize logs
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
2. Create CA and Certificates
```sh
docker-compose -f create-certs.yml run --rm create_certs
```
3. Build and Start ELK
```sh
docker-compose up -d
```

# How do I destroy this?

This will destroy all of ur data.
```sh
docker-compose down -v
```

# Supported Firewall Syslog ECS Conversions
- Check Point (Gaia Embedded)
- Fortinet
- Check Point (Gaia) - BETA

# Planned Features

- NGFW Feature ECS Conversion (IPS, AV, Emulation, Filtering, DNS Security)
- Palo Alto Syslog > ECS
- Cisco Syslog > ECS
- VyOS/Ubiquiti Edgerouter Syslog > ECS
