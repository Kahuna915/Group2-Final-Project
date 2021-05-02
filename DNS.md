### DNS Configuration
     - On mgmt01 navigate open server manager
     - In order to configure DNS you must have first added dc01 and dc02 to the mgmt server pool
     - In the top right of the server manager home page select "manage" and then select "Add Roles and Features"
     - Skip the "Before You Begin" page by clicking "Next"
     - Select "Rol-based or feature-based installation" and click "Next"
     - Make sure "Select a server from the server pool" is selected and then select the dc01-final server and then click "Next"
     - On the "Server Roles" page check the box that says "DNS Server" and then click "Next"
     - Skip past the "Features" page
     - Check the box at the top that restarts the server if necessary and click "Install"
     - Once the install is complete, repeat the process for dc02 and then navigate to the newly added DNS section on the left-hand side of the server manager
     - Right-click on Dc01 or Dc02 and select DNS manager
     - Go down to Reverse zone lookup
     - Here right-click on it and add a reverse zone for 172.16.1
     - After this go up to Forward lookup zones group2-final.local
     - In here right-click and hit add New AAA host
     - Type in all the Ip addresses and names assigned to you, this is the step where all of the hosts on your network are added to the DNS name server allowing you to identify the specific system by their hostname istead of their IP

![](https://github.com/CameronAuler/Group2-Final-Project/blob/ddb380942c471034bb74ea653217b32aa0d0e444/system-configuration/mgmt2/dns.PNG)