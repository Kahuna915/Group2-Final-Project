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
     - The file should look like . . .
network:
  version: 2

