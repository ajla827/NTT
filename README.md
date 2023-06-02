# Small Business Network

Building and configuring a SMB Network with a small team using GNS3 and FortiClient VPN. After the network was built and configured we ran a vulnerability scan top identify potential security issues. We algo used Dokuwiki to document network configurations and the vulnerability scan.

The client has requested the following:
- a secure network
- an internal Windows Domain
- an internal Microsoft IIS webserver
- an internal Windows 10 workstation
- a public webserver
- a public FTP server
- a LAN network on 10.128.0.0/24
- a DMZ network on 10.128.10.0/24
- a GUEST network on 10.128.99.0/24


---

### Starting topology

![image](https://github.com/ajla827/NTT/assets/129989031/cc494550-2157-496d-adf2-30e0b68a0255)

First we built the network infrastructure.

![image](https://github.com/ajla827/NTT/assets/129989031/d275d298-3584-40c9-91f1-78bab2b602b6)

After adding and connecting the Firewall and switches we configured the LAN network on the firewall through the CLI over the console interface.

![image](https://github.com/ajla827/NTT/assets/129989031/1901d0d3-4d20-4bbf-8723-ac5e0b0cb52a)

![image](https://github.com/ajla827/NTT/assets/129989031/d9afaa78-05d2-4eda-bd32-0c0073969f05)


