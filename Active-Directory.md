### Active Directory
     - On dc01 & dc02
     - Open up powershell by typing “powershell” in the command line
     - Then run: Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
     - After this run Install-ADDSForest -DomainName group2-final.local
     - On mgmt01 right-click on servers and select add new server
     - Add both Dc01 and Dc02

### Entering the AD
     - Just to show that we can. With Windows we know how to do it in the network settings, but it is a bit more complicated with non-windows systems.
     - We're gonna add the util machine here, which runs on CentOS 7. We have to download Realm and all of its friends like Python.: yum install sssd realmd oddjob oddjob-mkhomedir adcli samba-common samba-common-tools krb5-workstation openldap-clients policycoreutils-python -y. 
     - After that, we have to discover/resolve the domain. Look closely.

![](https://i.imgur.com/3lguLBF.jpg)

     - Once we resolve the domain, we need to join it.

![](https://i.imgur.com/aundq4L.jpg)

     - From there, we'll see it added to the Computers section of our AD which we can find in Active Directory Computers and Users.

![](https://i.imgur.com/IPdfaMP.jpg)

     - I've taken the liberty of moving it into the OU.