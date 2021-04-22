### Adding Servers:
     - Right-click on the server and hit add servers type in the IP address of dc01 and dc02
     - After they are connected make sure you installed these services on mgmt01:
     - Remote Server Administration Tools
     - AD DS and AD LDS Tools
     - DHCP Server Tools
     - DNS Server Tools
     - File Services Tools

### Creating admin accounts and groups:
     - In server manager click on AD DS
     - Right-click on either Dc01 or Dc02
     - Scroll down to users and right-click hit new user
     - Type in the information:
     - Then if you want the account to be an admin add it to the domain admin
     - Right Click on the domain and click new group:
     - Make it Linux-Admins
     - Add in domain admins to the group and then add in any accounts you want to be admins
