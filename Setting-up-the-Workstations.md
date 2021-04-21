### Set the network adapter in Vsphere to the proper LAN by . . .
     - Selecting the workstation in the "VM's and Templates" tab on the left-hand side of the Vsphere client interface
     - Right-click on the workstation
     - Select "Edit settings"
     - Change the network adapter 1 entry to the proper LAN(SYS265-03-LAN-SYS265-03-2FINAL for this project) using the drop-down menu
     - Then exit out of the settings tab

- Start The VM by selecting the green start button located to the right of the VM name
- Select the "Launch Web Console" button under the VM screen preview
- On the pop-up window, "Web Console" should be selected by default, but double-check and then select "OK"
- Log in to the workstation using the default username and the semester password

### For the configuration process of the workstation . . .
     - Open the control panel
     - Select "Network and Internet"
     - Select "Network and Sharing Center"
     - Select the "Ethernet0" connection or the "Change adapter settings" option on the left-hand side of the control panel interface
     - Select "Properties"
     - Click on "Internet Protocol Version 4 (TCP/IPv4)" to highlight it
     - Select "Properties"
     - Select the "Use the following IP address" option
     - Enter the static IP address for the workstation(172.16.1.100 and 172.16.1.150 for this project)
     - Enter the subnet mask(255.255.255.0 for this project)
     - Enter the default gateway(172.16.1.2 for this project as configured in the firewall configuration)
     - If the DNS server for your domain is set up then you can add a static DNS server address as well if necessary
     - To change the hostname, go back to the main control panel overview and select "System and Security"
     - Select "System"
     - In the "Computer name, domain, and workgroup settings" section, select "Change settings"
     - To change the hostname of the workstation, select the "Change..." button and change the "Computer name"(wks01-final and wks02-final for this project)
     - To change the domain select the "Domain" option and insert the name of your domain
     - To add a workstation to a domain, the active directory server needs to be configured and the domain needs to be set up