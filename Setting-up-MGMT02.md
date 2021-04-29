### Set the network adapter in Vsphere to the proper LAN by . . .
     - Selecting the mgmt02 VM in the "VM's and Templates" tab on the left-hand side of the Vsphere client interface
     - Right-click on mgmt02
     - Select "Edit settings"
     - Change the network adapter 1 entry to the proper LAN(SYS265-03-LAN-SYS265-03-2FINAL for this project) using the drop-down menu
     - Then exit out of the settings tab

- Start The VM by selecting the green start button located to the right of the VM name
- Select the "Launch Web Console" button under the VM screen preview
- On the pop-up window, "Web Console" should be selected by default, but double-check and then select "OK"
- Log in to the system using the username "champuser" and the semester password

### For the configuration process of MGMT02 . . .
     - Edit the "/etc/netplan/00-installer-config.yaml" file, command: "nano /etc/netplan/00-installer-config.yaml" or "vi /etc/netplan/00-installer-config.yaml"
     - The file should look like the image below
     - After configuring the file, edit the file "etc/hostname"(mgmt02-final for this project)
     - Run the command "sudo netplan apply" to apply all the configuration changes

### /etc/netplan/00-installer-config.yaml
![](https://github.com/CameronAuler/Group2-Final-Project/blob/8213752b7ec061d8e90ec22365ce98c83903ad80/system-configuration/mgmt2/mgmt02.PNG)