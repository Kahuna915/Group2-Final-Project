### Active Directory
     - On dc01 & dc02
     - Open up powershell by typing “powershell” in the command line
     - Then run: Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
     - After this run Install-ADDSForest -DomainName group2-final.local
     - On mgmt01 right-click on servers and select add new server
     - Add both Dc01 and Dc02