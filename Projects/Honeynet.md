<p style="text-align: center"><a href = "https://gafabic.github.io/Projects/index"><img src= "https://img.shields.io/badge/Projects-teal?style=for-the-badge"></a><a href="https://gafabic.github.io"><img src="https://img.shields.io/badge/Home-green?style=for-the-badge"></a><a href = "https://gafabic.github.io/Writeups/index"><img src = "https://img.shields.io/badge/Writeups-teal?style=for-the-badge"></a></p>

# Simple Honeynet

[Writeup of my findings can be found here.](../Writeups/HoneynetWriteup)

## Project goals:
- Gain experience configuring Microsoft Sentinel
- Gain experience investigating incidents with Sentinel
- Learn about attacker methodology from actual attacks

## Completed work:
- Configured Windows and Ubuntu machines with publicly accessible RDP and SSH ports
- Configured Sentinel and data connectors to provide audit and access logs
- Chose a user to permit attackers to access ("minecraft"), and enabled logging of commands run by users so that initial access and recon activity can be monitored

## ~~Next steps:~~
- ~~Choose a user to enable attacker access on Windows machine~~
- ~~Monitor attacks and investigate actions taken, try to fingerprint attacker profile.~~
- Azure trial credits have expired, project is currently on hiatus.

---
## Project updates

### 03/11/25:
Writeup of my findings from this project has been posted.

### 03/06/25:
Azure trial credits expired, unable to get any new data. I may revisit this project at some later time when a subscription is viable.

### 03/03/25:
Created honeypot user "minecraft" on Ubuntu machine and enabled command logging so as to analyze attacker behavior after landing on the machine. Also created an alert for Sentinel to inform me when someone logs in to this user.

Created a simple custom analytic in Sentinel to create an incident when someone logs in to the "minecraft" user.

### 02/21/25:
Created simple honeynet in Azure. Built two VMs - one Windows and one Linux, each running a remote access protocol (RDP and SSH, respectively) open to the internet. Set up Sentinel to collect access and audit logs from both machines to view incoming attempts to gain access.