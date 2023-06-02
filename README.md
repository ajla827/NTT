## Small Business Network

This is what I did in NTT class


![image](https://github.com/ajla827/NTT/assets/129989031/81db8a18-1d57-4d7c-83ae-be5d9c929583)

---
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

**Verify the configuration is correct:**

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

![image](https://github.com/ajla827/NTT/assets/129989031/6932195a-5e00-4d3c-8559-d617d3b572dd)


**Verify the configuration is correct:**

show sys dhcp server 1

![image](https://github.com/ajla827/NTT/assets/129989031/5b7e3539-61cc-4c50-9940-514a9aa80c25)

**Next Steps:**
Add new devices to the lab workspace, and link them up.
Configure the LAN network on the firewall through the CLI over the console interface.
Add a Win10 workstation to the LAN network.
Connect to the firewall GUI from the Win10 workstation.
Complete the network setup through the firewall GUI.

---
Refer to the GNS3 Guide Starting and Stopping devices in the lab workspace.
Start the Win10 workstation in GNS3, and then double click it to connect through VNC.
The first time you start Win10 it will take a minute or two to setup.
Click-and-hold the background image and drag up to show the login prompt.

**Login with the default credentials:**

Note: The username is already selected, you only need to enter the password.

Note: Close the OneDrive popup. You can ignore it, or disable it.

  username: IEUser
  
  password: Passw0rd!
  
  
 Verify the Win10 workstation has leased a DHCP address from the LAN network. 

  valid IP range: 10.128.0.[100-199]/24
  
  gateway: 10.128.0.1
  DHCP server: 10.128.0.1
  
![image](https://github.com/ajla827/NTT/assets/129989031/eb617d1f-f429-400f-968d-dbfd2781f3db)

**Test network connectivity:**

Ping remote destinations to test LAN, WAN, and DNS network connectivity.

  LAN - 10.128.0.1
  WAN - 8.8.8.8
  DNS - google.com
  
  LAN access should work.
  WAN and DNS should fail.

![image](https://github.com/ajla827/NTT/assets/129989031/77f171ad-f62a-4e5d-8e98-03437042b00d)

---
Connect to the GUI

Open the web browser on the Win10 workstation and connect to the firewall GUI.

  http://10.128.0.1/
  
  ![image](https://github.com/ajla827/NTT/assets/129989031/7b83cda2-8fac-405b-9bd0-af483e85e647)

Make system changes

Set the hostname and timezone.

Enable the NTP server service. This will allow LAN and DMZ devices to sync time with the firewall.

Set idle logout to 60 minutes. By default the GUI will auto logout after 5 minutes of inactivity, for the lab environment you should increase this to 60 minutes to avoid having to constantly log back into the GUI.

Enable auto file system check. This tells the firewall to run a system check during boot up. Enabling this prevents a nagging warning message that pops up during login after an unclean shutdown (powerloss/forced reboot/etc). Instead of sending a warning message, the firewall checks the system itself. In a production environment you might leave this disabled if you were concerned about peak performance for boot up.

Go to System > Settings.

Make the following changes:

  hostname = firewall
  timezone = GMT -6:00 Central Time (US & Canada)
  setup device as local NTP server = enabled
  setup device as local NTP server = enabled
  idle timeout = 60
  auto file system check = enabled

Backup the configuration

Click admin in the upper right corner of the GUI to take a backup of the firewall configuration.
Save the backup.
This will save to the Downloads folder on Win10.

![image](https://github.com/ajla827/NTT/assets/129989031/7bf3710e-cde0-4b99-9815-cb6e7e3ddc5f)

![image](https://github.com/ajla827/NTT/assets/129989031/c13a7666-61b6-4eb9-90b3-504c17c5699e)

---

![image](https://github.com/ajla827/NTT/assets/129989031/e71d16bf-35a6-4771-a928-d6c0bf291c85)


