### Set the network adapter in Vsphere to the proper LAN by . . .
     - Selecting the DHCP server in the "VM's and Templates" tab on the left-hand side of the Vsphere client interface
     - Right-click on the server
     - Select "Edit settings"
     - Change the network adapter 1 entry to the proper LAN(SYS265-03-LAN-SYS265-03-2FINAL for this project) using the drop-down menu
     - Then exit out of the settings tab

- Start The VM by selecting the green start button located to the right of the VM name
- Select the "Launch Web Console" button under the VM screen preview
- On the pop-up window, "Web Console" should be selected by default, but double-check and then select "OK"
- Log in to the server using the username "champuser" and the semester password

### For the configuration process of the DHCP server . . .
     - type the "nmtui" command into the terminal
     - Select "Edit a connection"
     - Select the ens192 connection under the "Ethernet" header
     - Using the arrow keys, navigate to the IPv4 configuration where it says "automatic"
     - Hit ENTER and select the "manual" option and hit ENTER again to confirm your choice
     - Navigate over to where it says "<show>" next to the IPv4 configuration and hit ENTER
     - Navigate back over to the IPv4 configuration section and fill in all of the necessary information
     - Addresses is the IPv4 address, make sure to add /24 or whatever your network prefix is at the end of the address(172.16.1.10/24 for this project)
     - Gateway is your default gateway(172.16.1.2 for this project)
     - For the primary DNS server, use 172.16.1.12 and 172.16.1.13 for the secondary DNS server
     - For the domain, use group2-final.local
     - Once you have configured the static IP navigate down to the bottom of the page to "<ok>" and hit enter
     - Navigate down to the bottom of the page to "<back>" and hit enter
     - Using the arrow keys, navigate to Set system hostname and hit ENTER
     - Delete the default hostname and type your own(DHCP01-group2-final & DHCP02-group2-final for this project)
     - Then go to "<ok>" and hit ENTER
     - Hit ENTER again to confirm
     - Make sure to run the command "systemctl restart network" or restart the server in order for the changes to be applied

![](https://github.com/CameronAuler/Group2-Final-Project/blob/2890aff826e32c77dd64a0d043109e2476ec0ce2/system-configuration/mgmt2/dhcp%20nmtui%20net%20config.PNG)

![](https://github.com/CameronAuler/Group2-Final-Project/blob/2890aff826e32c77dd64a0d043109e2476ec0ce2/system-configuration/mgmt2/dhcp%20nmtui%20hostname%20config.PNG)

### To create a non-root user with root privileges . . .
     - Make sure you are logged in as a root user
     - Type the "useradd username" command into the terminal, but replace username with the username of the user you want to add
     - Type the "passwd username" command into the terminal, but replace username with the username of the user you just created
     - The terminal will prompt you for the password you want to add for the user you just created
     - Type the password again in order to confirm it
     - Type the command "usermod -aG wheel username" into the terminal, but replace username with the username of the user you just created