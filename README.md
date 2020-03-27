# Ansible-Phantom-Base

This is an Ansible project that installs or upgrades Splunk Phantom to a specific version. It can also perform basic OS config (ulimits, THP disabled, firealld, hostname, etc.) in service of setting up a bare OS for Phantom to run on.


### Setup

1. Install Ansible
 
		- sudo apt-get install ansible (Ubuntu) 
		- sudo yum install ansible (CentOS)
		- brew install ansible (macOS)

2. git clone this project

		- git clone https://github.com/johnmcgovern/ansible-phantom-base.git	
	
3. Navigate to project base directory

		- cd ./ansible-phantom-base		

4. Copy hosts.sample to hosts

		- cp hosts.sample hosts

5. Edit hosts file to include desired hosts

		- vi hosts
	
6. Copy group_vars/all.sample to group_vars/all

		- cp group_vars/all.sample group_vars/all

7. Edit group_vars/all variables as appropriate for your enviornment

		- vi group_vars/all

8. Download the desired .tgz package from my.phantom.us and copy it to the ./ansible-phantom-base/files/ folder

		- cp -a ~/Downloads/phantom-4.8.23319-1.tgz ./files/	


### Usage
	
1. Navigate to playbook base directory

		- cd ./ansible-phantom-base
	
2. Run the Splunk Phantom install playbook

		- ansible-playbook -i hosts install.yml

3. -or- run the Splunk Phantom upgrade playbook

		- ansible-playbook -i hosts upgrade.yml

4. -or- run the OS initial configuration playbook

		- ansible-playbook -i hosts os-config.yml

5. -or- run an Ansible playbook limited to certain hosts within the hosts list

		- ansible-playbook -i hosts --limit=host1 install.yml


### Compatibility

This role is tested on:

- CentOS 7 1810


### Notes

- The goal of this role is to quickly execute a best-practices base Splunk Phantom install/upgrade.


### To-Do

- More systemd best practice settings coverage.


### Contact

- john@johnmcgovern.com or https://www.johnmcgovern.com
