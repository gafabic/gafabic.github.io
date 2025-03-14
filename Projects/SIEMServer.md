<p style="text-align: center"><a href = "https://gafabic.github.io/Projects/index"><img src= "https://img.shields.io/badge/Projects-teal?style=for-the-badge"></a><a href="https://gafabic.github.io"><img src="https://img.shields.io/badge/Home-green?style=for-the-badge"></a><a href = "https://gafabic.github.io/Writeups/index"><img src = "https://img.shields.io/badge/Writeups-teal?style=for-the-badge"></a></p>

# Homelab SIEM/EDR Server

## Project goals:
- To gain experience setting up and administering a SIEM and EDR system
- To gain experience tuning alarms on a SIEM
- Get firsthand experience looking over event logs in a SIEM for hacking activity

## Completed work:
- Set up hardware
- Installed and updated OS
- Installed Wazuh
- Tuned alerts:
	- Brute force alerts increased in severity level

## Next steps:
- Tune alerts regarding network scanning
- Monitor alerts, tune alert severity down for alerts that prove to be more noise than signal
- Run penetration tests to see what alerts populate from that activity, and tune alert severity accordingly.
- Add push notifications so I am alerted remotely whenever an alert of "high" or greater severity populates

---
## Project updates

### 10/9/24:
After running a brute force attack on another machine in my network, I noticed that the brute force alerts in Wazuh were listed as "medium" severity. Given that nothing inside my network should be logged into from outside the network, a brute force alarm would most certainly be an indication of an attack. Thus, I have increased the alert severity to "high" as it would merit more urgent investigation.

### 10/5/24:
I was able to source a Dell Poweredge R410 that my company was getting rid of which I was informed I could take for my own projects. I installed Ubuntu server on this device and then after making sure it was fully updated, installed Wazuh server, indexer, and dashboard on it. I then installed some agents on endpoint devices on my home network.