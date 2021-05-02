First step is installing the ansible package to MGMT02. To do so enter the command:

sudo apt install ansible sshpass python3-paramiko

SSH Set Up Instructions:

Create a user named deployer with a username and password.

Next is to edit the sudoers file. Enter the command "sudo vi /etc/sudoers" and add this line under root:

deployer  ALL=(ALL:ALL) ALL

For passwordless ssh, enter:

ssh-keygen -t rsa

Create the ".ssh" directory on remote machines if they don't already have it:

ssh deployer@(necessary machines) mkdir -p .ssh

Push public key to remote machines:

cat .ssh/id_rsa.pub | ssh deployer@(remote machines) 'cat >> .ssh/authorized_keys'

Set permissions if needed ssh deployer@(remote machines) "chmod 700 .ssh; chmod 640 .ssh/authorized_keys"
---------------------------------------------------------------------------------------------------------------------------------------------------------
Ansible Configuration:

Login as deployer and enter "cd /home/deployer". After, make a directory by inputting:

mkdir -p ansible/roles

Cd to that file (cd ansible/) and echo to "inventory.txt" using each remote machine name one by one:

(remote machine 1 hostname) >> inventory.txt
(remote machine 2 hostname) >> inventory.txt
etc

Group the hosts by Linux version within the "inventory.txt" file:

[Centos]
remote machine
remote machine...

[Ubuntu]
remote machine...

Enter command to install ansible playbook:

ansible-galaxy install semuadmin.webmin -p roles/