# Ansible-Phantom-Base

This Ansible project installs or upgrades Splunk SOAR (Phantom) to a specific version. It can also perform basic OS config (ulimits, THP disabled, firewalld, hostname, etc.) in service of configuring a bare OS for SOAR to run on. It is useful for  locally hosted development SOAR instances or SE lab environments.


### Setup

Install Ansible

 - sudo apt-get install ansible (Ubuntu)  - sudo yum install ansible (CentOS) - brew install ansible (macOS)
 
git clone this project

 - git clone https://github.com/johnmcgovern/ansible-phantom-base.git	
 
Navigate to project base directory

 - cd ./ansible-phantom-base		
 
Copy hosts.sample to hosts

 - cp hosts.sample hosts
 
Edit hosts file to include desired hosts

 - vi hosts
 
Copy group_vars/all.sample to group_vars/all

 - cp group_vars/all.sample group_vars/all
 
Edit group_vars/all variables as appropriate for your environment

 - vi group_vars/all
 
Download the desired .tgz package from my.phantom.us and copy it to the ./ansible-phantom-base/files/ folder
 - cp -a ~/Downloads/splunk_soar-unpriv-5.3.3.92213-ebef80f6-el7-x86_64.tar ./files/	


### Usage

Navigate to playbook base directory

 - cd ./ansible-phantom-base
 
Run the Splunk Phantom install playbook

 - ansible-playbook -i hosts install.yml
 
-or- run the Splunk Phantom upgrade playbook

 - ansible-playbook -i hosts upgrade.yml
 
-or- run the OS initial configuration playbook

 - ansible-playbook -i hosts os-config.yml
 
-or- run the OS config and Phantom install playbooks together

 - ansible-playbook -i hosts combo.yml
 
-or- install a valid SSL certificate (user provided)

 - ansible-playbook -i hosts tls-config.yml				
 
-or- run an Ansible playbook limited to certain hosts within the hosts list

 - ansible-playbook -i hosts --limit=host1 install.yml
 

### Compatibility
This role is tested on:
CentOS 7 1810


### Notes

The goal of this role is to quickly execute a best-practices base Splunk Phantom install/upgrade.
We now have the ability to (optionally) download the TGZ from a provided URL rather than upload it via the ./files/ folder. See group_vars/all for the required variables.
We also can now install an SSL cert (public/private key pair, PEM formatted) automatically using the ./certs/ folder. See group_vars/all for the required variables.


### To-Do
More systemd best practice settings coverage.

### Contact
john@johnmcgovern.com