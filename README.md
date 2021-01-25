# FireELK 🔥🦌
An ELK stack used for processing and visualizing firewall logs

# Details
- Provides a unified platform to ingest, parse, and visualize firewall logs
- Centralize multi-vendor logs
- Converts firewall syslog into the ECS (Elastic Common Schema) with Logstash
- Docker-Compose: Spins up a single node cluster of Elasticsearch, Logstash, Kibana
- Password Based X-Pack Security (The password is Letmein123!)

# Who should use this?
- Homelabbers who just want a simple functioning ELK stack
- Enterprises looking to test out the ELK stack
- Enterprises looking to not pay by the GB for fancy SIEMs
- Employees who want to show upper management cool dashboards during their performance review

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
