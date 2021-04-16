# DFS Configuration
### Vsphere Settings
> Set the network adapter in Vsphere to the proper LAN by . . .
     > Selecting the DFS server in the "VM's and Templates" tab on the left-hand side of the Vsphere client interface
     > Right-click on the DFS server
     > Select "Edit settings"
     > Change the network adapter 1 entry to the proper LAN(SYS265-03-LAN-SYS265-03-2FINAL for this project) using the drop-down menu
     > Then exit out of the settings tab

### Server Configuration
> Start The VM by selecting the green start button located to the right of the VM name
> Select the "Launch Web Console" button under the VM screen preview
> On the pop-up window, "Web Console" should be selected by default, but double-check and then select "OK"
> When the server core terminal loads, use the "Send Cntrl+Alt+Delete" button at the top right of the page to prompt login
> The terminal will prompt you to change the password of the "Administrator" account and then confirm your password
> For the configuration process of the server, Once you are in the command prompt terminal . . .
     > Use the "sconfig" command to open the server configuration interface
     > Select "Network Settings" by typing "8" into the terminal
     > Type the index number of the network interface you would like to configure(usually "1")
     > Select "1" again to "Set Network Adapter Address". This will allow you to configure a static IP address for the server
     > When prompted to select DHCP(D) or Static IP(S) select "s"
     > Enter the static IP for the server
     > Enter the Subnet mask(usually 255.255.255.0)
     > Enter the default gateway
     >You should now be brought back to the "Network Settings" Page

