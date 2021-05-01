    > On DHCP01 & DHCP02:
        > Run: yum install dhcp
        > Then do a vi /etc/dhcp/dhcpd.conf

![image](https://user-images.githubusercontent.com/62860262/116789069-1120e580-aa7b-11eb-9a92-7402a716f099.png)

        > Run systemctl start dhcpd
        > systemctl enable dhcpd
        > firewall-cmd --add-service=dhcp --permanent
        > firewall-cmd --reload