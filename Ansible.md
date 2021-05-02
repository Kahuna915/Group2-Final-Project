


First step is installing the ansible package to MGMT02. To do so enter the command:

sudo apt install ansible sshpass python3-paramiko

SSH Set Up Instructions
---------------------------------------------------------------------------------------------------------------------------------------------------------
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

Ansible Configuration
---------------------------------------------------------------------------------------------------------------------------------------------------------
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

Add user "deployer" to remote machines as well (using the same password unless you want to keep track of them all), and add it to the sudoers file using previous steps.

Creating the playbooks to install packages and create users
---------------------------------------------------------------------------------------------------------------------------------------------------------

Create 4 ".yml" files using touch:

touch create_userC.yml create_userU.yml playbook_apt.yml playbook_yum.yml

Open "create_userC.yml" with the text editor of your choice and enter the following code to create a playbook for adding users to your Centos machines:

(First line)
---
- name: Add users to Centos machines
  become: true
  hosts: Centos

  tasks:
    - name: Add user Bruce to Centos machine
      user:
       name: (Your choice)
       password: ''
       groups:
        - wheel
       state: present
       shell: /bin/bash
       system: no
       createhome: yes
       home: /home/(name)

Do the same for the Ubuntu machines in "create_userU.yml" but change the hosts to "Ubuntu" and groups to "sudo":

hosts: Ubuntu

groups:
 - sudo

Modify the "playbook_yum.yml file to install the yum package of your choice"

(First line)
---
- name: Playbook to run yum install command
  become: true
  hosts: Centos

  tasks:
  - name: Ensure (package) is installed through yum
    yum:
    name: (package)
    become: true
    become_method: su
    become_user: deployer

Modify the "playbook_apt.yml" file:

---
-name: Installs apt packages
 become: true
 become_method: su
 become_user: deployer
 hosts: Ubuntu

 tasks:
 - name: Install (package).
   become: true
   become_user: deployer
   package:
     name: (package)

Run playbooks:
---------------------------------------------------------------------------------------------------------------------------------------------------------

Now that the playbooks are set up you can run this command to the respective machines. For Example, if you want to add a user to Centos machines use this:

ansible-playbook -i inventory.txt create_userU.yml -K

BECOME password: (password of deployer)

After that you should get "ok" for each machine in Gathering Facts and should have "ok=1  changed=1" at the bottom which means that the playbook changed something on the remote hosts.

Check that the user is created by ssh to the remote host(s) and use "cat /etc/passwd". The user created should be at the bottom of the list.