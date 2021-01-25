# FireELK
An ELK stack used for processing and visualizing firewall logs

# Details
- Provides a unified platform to ingest, parse, and visualize firewall syslog
- Converts firewall syslog into the ECS (Elastic Common Schema)with Logstash
- Docker-Compose: Spins up a single node cluster of Elasticsearch, Logstash, Kibana
- Password Based X-Pack Security

# Supported Firewall Syslog ECS Conversions
- Check Point (Gaia Embedded)
- Fortinet
- Check Point (Gaia) - BETA

# Planned Features
- Palo Alto Syslog > ECS
- Cisco Syslog > ECS
- VyOS Syslog > ECS
- Certificate Based X-Pack Security
