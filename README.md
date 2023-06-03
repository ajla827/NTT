# Small Business Network

Building and configuring a SMB (small/medium business) Network with a small team using GNS3 and FortiClient VPN. After the network was built and configured, we ran a vulnerability scan to identify potential security issues. We algo used Dokuwiki to document network configurations and the vulnerability scan.

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

To the starting topology we added a LAN, DMZ, and Guest network. Using the FortiNet firewall CLI we configured the LAN interface and DHCP server. We also added a Windows domain environment, an IIS server, a Windows FTP server, a Win10 workstation, a LAMP webserver running UNBUNTU hosting a dokuwiki, and a Fortigate firewall with a VIP for a DMZ webserver. To finalize the project we hardened the environment, ran a vulnerability test, documented the findings and completed research on how to correct the vulnerabilities according to the vendors.

Configured the LAN network on the firewall through the CLI over the console interface and configured the DHCP server for the LAN interface.

![image](https://github.com/ajla827/NTT/assets/129989031/1901d0d3-4d20-4bbf-8723-ac5e0b0cb52a)

![image](https://github.com/ajla827/NTT/assets/129989031/d9afaa78-05d2-4eda-bd32-0c0073969f05)

![image](https://github.com/ajla827/NTT/assets/129989031/6eaa1807-b29b-497b-843f-8d55bfde1e68)

![image](https://github.com/ajla827/NTT/assets/129989031/9bc23b06-1e40-4649-a6be-2ac5a752e3b9)

---

Using the Firewall GUI we configured network interfaces, enabled DNS, configured the firewall system DNS and network DNS, created Service Objects, configured firewall rules, and backed up the firewall configurations.

![image](https://github.com/ajla827/NTT/assets/129989031/3106d773-3b8f-456d-9c49-81c9da1dfdbf)

![image](https://github.com/ajla827/NTT/assets/129989031/c6202f16-29cc-406e-917b-fea8038a7443)

![image](https://github.com/ajla827/NTT/assets/129989031/f82771bf-30ce-4a84-b9ef-46fc603d601f)

![image](https://github.com/ajla827/NTT/assets/129989031/c11b78b0-9cca-4b17-b84f-d384238f630b)

---

Setting up the Domain Controller.

![image](https://github.com/ajla827/SMB-Network-Project/assets/129989031/8d29112b-e824-44a0-83a8-d64608a48cdf)

![image](https://github.com/ajla827/SMB-Network-Project/assets/129989031/2f5959db-cb8b-40cd-8210-a45ecde164a4)

![image](https://github.com/ajla827/SMB-Network-Project/assets/129989031/39a77ec8-a42f-43b4-b3bf-4b37cfbc4bda)

![image](https://github.com/ajla827/SMB-Network-Project/assets/129989031/5d988ff9-c1ef-4487-9d51-7320e5bde5f9)

![image](https://github.com/ajla827/SMB-Network-Project/assets/129989031/cacbb2cb-075f-46dc-a224-b2b53a915e90)

![image](https://github.com/ajla827/SMB-Network-Project/assets/129989031/05482c9e-19cd-40d9-80d8-61e49530e60e)

---

We installed Active Directory and created users, admins, and group policies.

![image](https://github.com/ajla827/SMB-Network-Project/assets/129989031/f88f444b-930f-45d7-8d03-840e13492d21)

![image](https://github.com/ajla827/SMB-Network-Project/assets/129989031/261dfaa2-0671-489e-9daf-239b8dc7c55a)

---

We added and prepared another WIN 2012 Server to join the domain and installed the Internet Information Services (IIS) server role.

![image](https://github.com/ajla827/SMB-Network-Project/assets/129989031/fd3211da-227d-446e-8257-19162cd8d408)

---

Next, we built a LAMP (Linux, Apache, MySQL, PHP/Perl/Python) webserver on Ubuntu server inside our DMZ network.

![image](https://github.com/ajla827/SMB-Network-Project/assets/129989031/1c59abe0-1548-44f5-984e-7ab530ee7dcb)

![image](https://github.com/ajla827/SMB-Network-Project/assets/129989031/f1fa45d3-c736-4f88-bc73-10279cf542e9)

---

Throughout the process we kept documenting what we were configuring and the findings of the vulnerability scan in DokuWiki.

![image](https://github.com/ajla827/SMB-Network-Project/assets/129989031/ba48a220-31cd-4c20-9cbd-34e9569df20f)

---

The last server we built and configure was the FTP server on the DMZ network. 

![image](https://github.com/ajla827/SMB-Network-Project/assets/129989031/fd799c69-4f17-464d-a981-5a194d0fb841)

---

After completing our SMB network we ran a vulnerability scan using Greebone so we can further secure our networks.

![image](https://github.com/ajla827/SMB-Network-Project/assets/129989031/96fbbf73-737f-44ff-bc26-ae5a0e337080)

![image](https://github.com/ajla827/SMB-Network-Project/assets/129989031/ee3c7e53-fa0a-4b27-8da1-c3b59b11a47f)

![image](https://github.com/ajla827/SMB-Network-Project/assets/129989031/e77a7800-b6ad-4a61-938b-4051be9df78c)
