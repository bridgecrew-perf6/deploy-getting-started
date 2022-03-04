# deploy-getting-started
Ansible playbook to deploy this app on a compute instance using docker: 
https://github.com/docker/getting-started


A static volume is used for the sqlite database

# Installation
This is a standalone running shipped version

## Requirements
Installed on your local PC:
* Vagrant
* Oracle Virtualbox

## Instructions
1. Download this repo somewhere to your pc
2. From that folder run `vagrant up`
3. Open your Browser and enter http://127.0.0.1:9000/
4. Enter some items to the todo list
5. Re-provision the vm using `vagrant up --provision`
6. validate that your previous entered items are still there

# Description
## Vagrant
Vagrant validates the `Vagrantfile` and configures the network (bridged is used). Next its installing ansible and some ansible-galaxy items: 
- geerlingguy.docker: installs docker on a system
- community.docker: provides some nice ansible modules

After the ansible installation is done, the playbook is getting executed.

## Ansible
A port for the app can be configured in `ansible/hostvars/localhost.yml`
