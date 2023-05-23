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


![image](https://github.com/ajla827/NTT/assets/129989031/4c62f24e-b60f-4259-9f81-d341b0d94028)

Verify the configuration is correct:

show sys int port2

![image](https://github.com/ajla827/NTT/assets/129989031/a73b9d16-1a88-4c51-98e5-2095bb83f6de)

Configure the DHCP server for the LAN interface:
Enable the DHCP sever on the LAN interface.
The firewall will perform DHCP services for devices on the LAN network.
Set the DHCP pool scope to 10.128.0.[100-199].
Note: There is no particular reason for the [100-199] range, it just sets boundaries to work within. In a production environment it is much easier to expand a DHCP range that in is to contract.

conf sys dhcp server

      edit 1
      
          set default-gateway 10.128.0.1
          
          set netmask 255.255.255.0
          
          set interface port2
          
          config ip-range
          
              edit 1
              
                  set start-ip 10.128.0.100
                  
                  set end-ip 10.128.0.199
                  
              next
              
          end
          
      next
      
  end
