
 🛡️ 🛡️ Simple SOC Lab Setup – Ready for Log Ingestion

This project documents the initial setup of a basic Security Operations Center (SOC) lab focused on centralized log ingestion, analysis, and visualization using the Elastic Stack.

![Initial Step](screenshots/day01.png)  
*Day 1 Initial SOC Lab Setup:   This stage establishes the foundational infrastructure required to begin collecting and analyzing security logs.*
🧱 SOC Lab Architecture

The SOC lab architecture includes:

Cloud-hosted Ubuntu server

Elasticsearch for log ingestion and indexing

Kibana for visualization and analysis

Secure SSH access from a local macOS system

VPC networking for isolation and scalability

![Architecture](https://github.com/Jaysolex/30-Day-SOC-Challenge/blob/main/screenshots/Lab%20Architech.png)  
*Overall SOC Lab Architecture*

![Vultr – Ubuntu + VPC 2.0](https://github.com/Jaysolex/30-Day-SOC-Challenge/blob/main/screenshots/Vultr%20cloud%20running%20OS%20and%20VPC.png)  

*Vultr cloud instance running Ubuntu OS with VPC 2.0 networking*


☁️ Cloud Infrastructure (Vultr)

Ubuntu Server deployed on Vultr

VPC 2.0 enabled for private networking

Instance serves as the central SOC log ingestion and analysis node

🔐 Elastic Stack Access via SSH

Elasticsearch and Kibana are installed and managed directly on the Ubuntu server using SSH access from a macOS terminal.

![Elasticsearch & Kibana via SSH](https://github.com/Jaysolex/30-Day-SOC-Challenge/blob/main/screenshots/Elastic%20search%20and%20Kibana%20running%20via%20SSH%20from%20mac%20terminal%20into%20ubuntu%20on%20Vultr.png)  
*Accessing Elasticsearch and Kibana on the Vultr Ubuntu instance via SSH from a Mac terminal*


![Elastic Dashboard](https://github.com/Jaysolex/30-Day-SOC-Challenge/raw/main/screenshots/Elastic%20dashboard.png)  
*Elastic Dashboard showing collected logs, visualizations, and detections*

The Kibana dashboard confirms:

Successful Elasticsearch indexing

Kibana service availability

Readiness for log ingestion, dashboards, and detections


```bash
# Connect to Vultr Ubuntu server from Mac terminal
ssh root@<VULTR_SERVER_IP>

# Update and upgrade system
sudo apt update && sudo apt upgrade -y

# Start Elasticsearch
sudo systemctl start elasticsearch
sudo systemctl enable elasticsearch

# Start Kibana
sudo systemctl start kibana
sudo systemctl enable kibana

# Verify Elasticsearch
curl -X GET "localhost:9200/"

# Verify Kibana
curl -X GET "localhost:5601/"

---
