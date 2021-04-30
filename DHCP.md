This is the DHCP configuration page!
    > On DHCP01 & DHCP02:
        > Run: Install-WindowsFeature DHCP -IncludeManagementTools
    > Go to mgmt1
        > Now DHCP should show up...if not refresh
        > Now in active directory add in DHCP tools under features --> Remote Server admin tools
        > Enter the new scope which is 172.16.5.100 to 172.16.5.150 and enter the dns and then promote the server. 
        > Run ipconfig /renew after setting everything to automatic
