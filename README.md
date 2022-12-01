# MySQL_installation_Ansible and Change Datadir to new location

1) MySQL initial setup and configuration
Reference: https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-22-04

Requirements:
 - Ansible Master node (Ubuntu 22.04) with Ansible 2.10.8 installed
 - Ansible slave/remote nodes (Ubuntu 22.04) should have passwordless access from Ansible master
 
ansible-playbook -i inventory mysql_installation.yml

The above playbook execution does the below things in all the remote hosts specidied in the inventory file
- Installs MySQL server and Python3-mysql package
- Sets MySQL root user password
- Configure mysql_secure_installation
- Creates new user with All priveleges
- Checks and provides the MySQL version installed

<img width="828" alt="image" src="https://user-images.githubusercontent.com/98776326/205132564-c8d15d99-66b0-4913-a4b1-74b1bb167828.png">
