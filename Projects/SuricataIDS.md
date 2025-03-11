<p style="text-align: center"><a href = "https://gafabic.github.io/Projects/index"><img src= "https://img.shields.io/badge/Projects-teal?style=for-the-badge"></a><a href="https://gafabic.github.io"><img src="https://img.shields.io/badge/Home-green?style=for-the-badge"></a><a href = "https://gafabic.github.io/Writeups/index"><img src = "https://img.shields.io/badge/Writeups-teal?style=for-the-badge"></a></p>

# Suricata IDS

## Project goals:
- Gain experience with IDS systems
- Add monitoring of network traffic to my SIEM capabilities

## Completed work:
- Installed Suricata on Ubuntu server in lab
- Configure Suricata server to send data to <a href = "SIEMServer">Wazuh server</a> via agent

## Next steps:
- Configure ubuntu server to operate in promiscuous mode
- Tune Suricata rules and alerts based on network scanning activity

---
## Project updates

### 11/18/24:
Installed Suricata on a Ubuntu container in my pentesting lab. Also installed ET rules and a wazuh agent so that suricata logs and alerts are reported to my SIEM.