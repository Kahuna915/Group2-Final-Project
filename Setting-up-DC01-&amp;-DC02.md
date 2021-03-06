### Set the network adapter in Vsphere to the proper LAN by . . .
     - Selecting the dc server in the "VM's and Templates" tab on the left-hand side of the Vsphere client interface
     - Right-click on the server
     - Select "Edit settings"
     - Change the network adapter 1 entry to the proper LAN(SYS265-03-LAN-SYS265-03-2FINAL for this project) using the drop-down menu
     - Then exit out of the settings tab

- Start The VM by selecting the green start button located to the right of the VM name
- Select the "Launch Web Console" button under the VM screen preview
- On the pop-up window, "Web Console" should be selected by default, but double-check and then select "OK"
- When the server core terminal loads, use the "Send Cntrl+Alt+Delete" button at the top right of the page to prompt login
- The terminal will prompt you to change the password of the "Administrator" account and then confirm your password

### For the configuration process of the server, Once you are in the command prompt terminal . . .
     - Use the "sconfig" command to open the server configuration interface
     - Select "Network Settings" by typing "8" into the terminal
     - Type the index number of the network interface you would like to configure(usually "1")
     - Select "1" again to "Set Network Adapter Address"
     - When prompted to select "DHCP(D) or Static IP(S)" select "s"
     - Enter the static IP for the server(172.16.1.12, 172.16.1.13 for this project)
     - Enter the Subnet mask(usually 255.255.255.0)
     - Enter the default gateway(172.16.1.2 for this project)
     - You should now be brought back to the "Network Settings" interface
     - Select "4" to "Return to Main Menu"
     - Select "2" to "Set DNS Servers"
     - When prompted to "Enter new DNS server" put the IP address of the DNS server for your domain(172.16.1.14 for this project)
     - When Prompted to "Enter alternate DNS server" put the IP address of the secondary DNS server(172.16.1.13 for this project)
     - You should now be brought back to the "Main Menu" interface

![](https://github.com/CameronAuler/Group2-Final-Project/blob/2890aff826e32c77dd64a0d043109e2476ec0ce2/system-configuration/mgmt2/dc%20sconfig%20network.PNG)

     - Select "Domain/Workgroup" by typing "1" into the terminal
     - When prompted to "Join (D)omain or (W)orkgroup" select "d"
     - Enter the name of your domain(group2-final.local for this project)
     - When prompted to enter "an authorized domain\user" use a domain account with admin privileges
     - You will then be prompted for the password of the admin account that you used
     - You should now be brought back to the "Main Menu" interface

     - Select "Computer Name" by typing "2" into the terminal
     - Enter the new hostname for the server(dc01-final and dc02-final for this project)
     - A notification will pop up asking you to restart the server, select "yes"

![](https://github.com/CameronAuler/Group2-Final-Project/blob/2890aff826e32c77dd64a0d043109e2476ec0ce2/system-configuration/mgmt2/dc%20sconfig%20main.PNG)

     - When you log back into the server using the password that you created before, all of the settings should be complete
     - Run the command "ipconfig /all" again to check if the static IP you set has the "(preferred)" identifier
     - Run "sconfig" again to check if the domain and hostname were set properly
     - You might also want to ping external hosts as well as hosts on your domain using their hostname to verify the successful domain configuration

### To setup Active Directory . . .
     - Make sure you are on the basic command line
     - Open PowerShell by typing the command "powershell" into the terminal
     - Once in the PowerShell terminal, run the command "Install-WindowsFeature AD-Domain-Services -IncludeManagementTools"
     - After the completion of that command, run the command "Install-ADDSForest -DomainName group2-final.local"