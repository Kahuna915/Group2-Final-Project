### What we do first go to your firewall machine
    > Set the network adapters in vsphere to WAN & LAN, (if there is only one network adapter hit edit and add new device)
    > Turn the machine on - you then will be prompted with many choice    
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
