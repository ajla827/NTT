## NTT

This is what I did in NTT class


![image](https://github.com/ajla827/NTT/assets/129989031/81db8a18-1d57-4d7c-83ae-be5d9c929583)


On a physical firewall the LAN interface is usually preconfigured. On a virtualized firewall you usually have to manually configure it. Once the LAN interface has been configured you will be able to access the firewall GUI from a device on the LAN.

Per the clients request you will configure 10.128.0.0/24 as the LAN network.
The LAN gateway will be 10.128.0.1/24.
The LAN interface is named port2 on the FortiGate firewall.

conf sys int

      edit port2
      
          set allowaccess ping http https ssh
          
          set ip 10.128.0.1/24
          
      end
