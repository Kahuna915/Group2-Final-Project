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
        > Select option 2 and pick the WAN first
            > Configure IPv4 via DHCP: n
            > Enter your IPv4 address
            > Enter the subnet: 24
            > Enter upstream gateway: 10.0.17.2
            > Configure IPv6 addresses with DHCPV6: n
            > Skip the WAN IPv6 address
            > Revert to HTTP: n
        > Pick option 2 again and this time select the LAN
            > Enter IPv4 address & subnet 
            > Hit enter twice
            > Enable DHCP server on LAN: N
            > Revert to HTTP webConfig: N
