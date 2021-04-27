# Welcome to the Group2-Final-Project wiki!
### Basic Configuration Documentation
* [[Networking and Configuration]]

### Service Configuration Documentation
* [[Service Configuration]]

### Domain Policy!
* [[Group Domain Policy]]

### Tests
* [[Tests]]


# RVTM Test Plan
|  requirement  |  Description  |  Test  |
|  -----------  |  -----------  |  ----  |
|  1. Redundant AD infrastructure  |  Redundant AD infrastructure using [DC1 + DC2](https://github.com/CameronAuler/Group2-Final-Project/wiki/Setting-up-DC01-%26amp%3B-DC02). One should be able to turn off DC1 or DC2, and still be able to manage AD and login via W1 + W2 + MGMT1.  |  |
| 2. DHCP | [DHCP1 and DHCP2](https://github.com/CameronAuler/Group2-Final-Project/wiki/Setting-up-DHCP01-%26amp%3B-DHCP02) should provide DHCP services to your LAN. They should also be redundant. Turn off DHCP1 or 2 and ipconfig/release and /renew from W1. |  |
| 3. Ansible Interactive | MGMT2 will be an Ansible controller system that can control your entire domain (including the firewall), with the exception of Windows workstations. You should be able to run interactive commands against all these systems. |  |
| 4. Util and Ansible Deploy |  Util will be a system that you can provision with a new application via MGMT2 and Ansible. It can also be used to assist in meeting other requirements. Deploy an application that has not been covered in class to util using an Ansible playbook. |  |
| 5. AD Infrastructure | MGMT1, DC1, DC2, DFS1, DFS2 and your workstations represent your Active Directory Infrastructure. Your domain should be your groupname.local. Join all windows systems to the domain and at least one of your Linux systems. |  |
| 6. Group Sudo | Create an AD security group called linux-admins. Members of this group should be able to sudo to root on one of your Linux systems (this has some implied sub-requirements). |  |
| 7. Docker Wiki | Install docker and a wiki/application of your choice (Not WordPress!) on docker. |  |
| 8. GPO Wallpaper | Create a Domain Group Policy that applies corporate wallpaper to W1 + W2 + MGMT1. |  |
| 9. Domain Group Policy | Create a Domain Group Policy that allows W1 + W2 to remote desktop between one another. |  |
| 10. Profiles and Shares on DFS | Create a Domain group policy that moves W1 and W2 user profiles and home directories to a DFS share. |  |
| 11. apt | Use Ansible to install an apt-package. |  |
| 12. yum | Use Ansible to install a yum package. |  |
| 13. Linux Local | Use Ansible to add a new Linux local user can be an SSH user or one with a password. |  |
| 14. Domain User | Use Ansible to add a new Windows domain user. |  |