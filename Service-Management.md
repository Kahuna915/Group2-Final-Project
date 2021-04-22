### Adding Servers:
     - Right-click on the server and hit add servers type in the IP address of dc01 and dc02
     - After they are connected make sure you installed these services on mgmt01:
     - Remote Server Administration Tools
     - AD DS and AD LDS Tools
     - DHCP Server Tools
     - DNS Server Tools
     - File Services Tools

### Adding Workstations
     - Domain join them by:
          - In Powershell run Add-Computer -DomainName “group2-final.local” -restart
          - Put in the credentials
     - Or:
          - Open Control panel go to system and security then to system
          - Under computer name, domain and workgroup click change settings
          - Under member of click domain type in your domain name and sign in to an admin account
          - Then restart your computer (you can also change the computer's name from this section)

### Creating admin accounts and groups:
     - In server manager click on AD DS
     - Right-click on either Dc01 or Dc02
     - Scroll down to users and right-click hit new user
     - Type in the information:
     - Then if you want the account to be an admin add it to the domain admin
     - Right Click on the domain and click new group:
     - Make it Linux-Admins
     - Add in domain admins to the group and then add in any accounts you want to be admins
