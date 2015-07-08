#Sun Grid Engine 

Install and Configure Sun Grid Engine on Ubuntu 12.04 Cluster

**Ubunut 12.04 LTS Vagrant box**

Check that you can get Ubuntu Precise 64 from 

	$ vagrant init ubuntu/precise64; vagrant up --provider virtualbox

**Install Ansible**
 
Ubuntu LTS 12.04

     $ sudo apt-get install software-properties-common
     $ sudo apt-add-repository ppa:ansible/ansible
     $ sudo apt-get update
     $ sudo apt-get install ansible

Other Linux Distributions

to install on another Linux Distribution check out [Ansible Docs](http://docs.ansible.com/intro_installation.html)

**Hosts File**

Here is a sample of hosts file

	[servers]
	master  ansible_ssh_host=192.168.0.10 ansible_ssh_user=vagrant  ansible_ssh_pass=vagrant
	slave1  ansible_ssh_host=192.168.0.11 ansible_ssh_user=vagrant  ansible_ssh_pass=vagrant
	slave2  ansible_ssh_host=192.168.0.12 ansible_ssh_user=vagrant  ansible_ssh_pass=vagrant

	[masters]
	master  ansible_ssh_host=192.168.0.10 ansible_ssh_user=vagrant  ansible_ssh_pass=vagrant

	[slaves]
	slave1  ansible_ssh_host=192.168.0.11 ansible_ssh_user=vagrant  ansible_ssh_pass=vagrant
	slave2  ansible_ssh_host=192.168.0.12 ansible_ssh_user=vagrant  ansible_ssh_pass=vagrant

**Configure Passwordless SSH**

This section shows how to make a passwordless SSH among cluster's nodes.

     $ ssh-keygen -t rsa
     $ cp ~/.ssh/id_rsa* roles/common/files/
   
**Setup SGE Cluster**

Finally, setup your Sun Grid Engine Cluster using Ansible

    $ ansible-playbook -i hosts playbook.yml -vvvv
