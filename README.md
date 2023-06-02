# Small Business Network

Building and configuring a SMB (small/medium business) Network with a small team using GNS3 and FortiClient VPN. After the network was built and configured we ran a vulnerability scan top identify potential security issues. We algo used Dokuwiki to document network configurations and the vulnerability scan.

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

### Final topology

![image](https://github.com/ajla827/NTT/assets/129989031/622ed26c-9f1e-43ba-872b-a6ddbee1e5e6)


After adding and connecting the Firewall and switches we configured the LAN network on the firewall through the CLI over the console interface and configured the DHCP server for the LAN interface.

![image](https://github.com/ajla827/NTT/assets/129989031/1901d0d3-4d20-4bbf-8723-ac5e0b0cb52a)

![image](https://github.com/ajla827/NTT/assets/129989031/d9afaa78-05d2-4eda-bd32-0c0073969f05)

![image](https://github.com/ajla827/NTT/assets/129989031/6eaa1807-b29b-497b-843f-8d55bfde1e68)

![image](https://github.com/ajla827/NTT/assets/129989031/9bc23b06-1e40-4649-a6be-2ac5a752e3b9)

LAN, DMZ, and Guest network. Utilized a FortiNet firewall and configured both static and dynamic IP address for systems. Configured the interfaces in CLI and we configured the LAN interface and verified it was correct. We also created a Windows domain environment, an IIS server, a Windows FTP server, a Win10 workstation, a LAMP webserver running UNBUNTU, hosting a wiki, a Fortigate firewall, with a VIP for a DMZ webserver
