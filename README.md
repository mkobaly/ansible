# ansible
Scratchpad repository to get familiar with Ansible. To get started I was working with
Consul to setup a new cluster.

### Gotchas
- Ensure you can ssh into each server first
- strugggled getting some tasks run. Passing -K to command line allowed me to pass password but not sure this is best practice
- was unable to get role working that was part of site.yml (brianshumate.consul)
- in hosts you need to ensure ethernet name correct (type one of the 3 below commands)

    ip addr or ifconfig or ip link

#### [Downloading custom galaxy roles](https://galaxy.ansible.com/intro#download)
Place all of the roles wanted in a file (roles.yml) and execute below command
    
    sudo ansible-galaxy install -r roles.yml

### Installing a playbook
- test.yml is the file containing the role(s) we want 
- hosts file lists out the servers participating

Note: hosts file must have section matching what is defined in consul.yml file

    ansible-playbook -i hosts consul.yml -K  