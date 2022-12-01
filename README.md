# MySQL installation using Ansible and Changes Datadir to new location

## 1) MySQL initial setup and configuration
Reference: https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-22-04

### Prerequisites:
 - Ansible Master node (Ubuntu 22.04) with Ansible 2.10.8 installed
 - Ansible slave/remote nodes (Ubuntu 22.04) should have passwordless access from Ansible master
 
>ansible-playbook -i inventory mysql_installation.yml

<img width="828" alt="image" src="https://user-images.githubusercontent.com/98776326/205132564-c8d15d99-66b0-4913-a4b1-74b1bb167828.png">

## 2) Setting New Data directory for MySQL
Reference: https://www.digitalocean.com/community/tutorials/how-to-move-a-mysql-data-directory-to-a-new-location-on-ubuntu-20-04

### Prerequisites:
- Ansible Master node (Ubuntu 22.04) with Ansible 2.10.8 installed
- Ansible slave/remote nodes (Ubuntu 22.04) should have passwordless access from Ansible master
- Ansible slave nodes should have MySQL installed and Running
- A MySQL username and password is required with all privileges

>ansible-playbook -i inventory Change_MySQL_datadir.yml --extra-vars "old_dir=/var/lib/mysql new_dir=/tmp"

While running this playbook --extra-vars should be specified.
1) old_dir = Current Datadir (Can be found using "select @@Datadir")
2) new_dir = New Datadir

<img width="686" alt="image" src="https://user-images.githubusercontent.com/98776326/205133926-7023ce67-61c6-42d4-bf04-2e0aa7614e37.png">
