<p style="text-align: center"><a href = "https://gafabic.github.io/Projects/index"><img src= "https://img.shields.io/badge/Projects-teal?style=for-the-badge"></a><a href="https://gafabic.github.io"><img src="https://img.shields.io/badge/Home-green?style=for-the-badge"></a><a href = "https://gafabic.github.io/Writeups/index"><img src = "https://img.shields.io/badge/Writeups-teal?style=for-the-badge"></a></p>

# DNS Server/PiHole

## Project goals:
- Get experience installing and wsorking with ProxMox and Type 1 hypervisors
- Make network administration easier by using FQDNs instead of memorizing IP addresses
- Get more experience administering DNS locally
- Increase privacy and speed of internet usage while gaining experience with DNS sinkholes

## Completed work:
- Installed ProxMox hypervisor on server
- Installed pihole as container on hypervisor
- Set pihole as local DNS server
- Added Wazuh agent on hypervisor and DNS server for security monitoring

## Next steps:
- Add further sinkhole lists to pihole to increase effectiveness of ad and tracker blocking

---
## Project updates

### 10/25/24:
I have installed ProxMox on a Dell PowerEdge R610. This posed a number of challenges, as installation was a little tricky. Challenges posed were as follows:

- Unlike previous servers I have worked with, R610 server requires drives be added as logical disks. Had to figure this out in order to be able to view block devices.
- ProxMox installation on R610 was finicky and kept failing. After research on stackoverfow, discovered that I could get installation to complete if I disabled virtualization in bios, and then re-enable it after completed install.
- After successful installation, server was not using correct NIC. Updated configs to bridge `vmbr` with `eno1`, network connectivity began to work properly.

After installation of ProxMox, I configured a Debian 12 container on the hypervisor and installed pihole. This setup was fortunately simple and after allocating a static IP to the container on my router, I was able to configure the router to use it as the default DNS server. However, I did run into yet another complication:

- After setting the pihole as my DNS server and adding my local domains to the DNS records, I found that my laptop was still not resolving the domains to their IP addresses. I was able to confirm that the server had the A records properly set by doing a `nslookup` specifying the pihole as nameserver. However, when not specifically specifying this, I found that nslookup was using a different DNS server than what had been configured.
	+ After further digging via `ipconfig /all`, I discovered that my laptop was being allocated a pair of IPv6 addresses for DNS servers that I had not specified. Digging around online, I was able to learn that this was being broadcast out by my router to any device that is using IPv6. Furthermore, it seems that the netgear router in question does not give the end user the ability to disable this. Barring getting a new router, I found that the best way to circumvent this issue for my purposes is to disable IPv6 on my home lab. Doing so, I am now able to properly resolve my local domain names.