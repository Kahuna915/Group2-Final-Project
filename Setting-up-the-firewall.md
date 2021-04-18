### Set the network adapters in Vsphere to the proper LAN and WAN by . . .
     - Selecting the firewall in the "VM's and Templates" tab on the left-hand side of the Vsphere client interface
     - Right-click on the firewall
     - Select "Edit settings"
     - If there is only one network adapter, select "ADD NEW DEVICE" and then add a network adapter
     - Change the network adapter 1 entry to the proper WAN(SYS265-03-WAN for this project) using the drop-down menu
     - Change the network adapter 1 entry to the proper LAN(SYS265-03-LAN-SYS265-03-2FINAL for this project)
     - Then exit out of the settings tab

- Start The VM by selecting the green start button located to the right of the VM name
- Select the "Launch Web Console" button under the VM screen preview
- On the pop-up window, "Web Console" should be selected by default, but double-check and then select "OK"

### To configure the firewall . . .
     - When the firewall interface loads, a menu of the different configuration options will appear prompting you to "enter an option"
     - Select "Set interface(s) IP address" by selecting option "2"
     - When prompted to "Enter the number of the interface you wish to configure" select "1" to configure the WAN
     - When prompted to "Configure IPv4 via DHCP" select "n"
     - The Firewall should now be configured
     - Enter the static IP for the WAN interface of the firewall(172.16.1.2 for this project)
     - Enter the subnet prefix(24 for this project)
     - Enter the upstream gateway(10.0.17.2 for this project)
     - When prompted to "Configure IPv4 addresses with DHCPv6" select "n"
     - Skip the Wan IPv6 address
     - When prompted to "Revert to HTTP" select "n"
     - You should now be brought back to the main firewall interface
     - Select "Set interface(s) IP address" by selecting option "2" again
     - When prompted to "Enter the number of the interface you wish to configure" select "2" to configure the LAN
     - When prompted to "Configure IPv4 via DHCP" select "n"
     - Enter the static IP for the LAN interface of the firewall(172.16.1.2 for this project)
     - Enter the subnet prefix(24 for this project)
     - Skip the upstream gateway setup and the IPv6 address setup
     - When prompted to "Enable the DHCP server on LAN" select "n"
     - When prompted to "Revert to HTTP" select "n"