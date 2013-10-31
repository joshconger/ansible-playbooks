# Andrew Wood's Ansible Playbooks

This is a set of Ansible playbooks for provisioning and configuring various
CentOS application servers.


## Getting Started

1. You'll need to install Ansible.  
[http://www.ansibleworks.com/docs/intro_installation.html](http://)

2. Make sure your ssh public key is copied to your server(s) and your ssh hosts file `~/.ssh/config` has an entry for the servers you are building.

3. Decide where you're going to define your hosts file for Ansible (refer to [Ansible docs](http://www.ansibleworks.com/docs/intro_installation.html)). Instead of the default `/etc/ansible/hosts`, I usually create host files named `test` and `prod` so I can select which group of servers I am targetting using the `-i` switch.  
Example: `ansible-playbook -i prod lemp.yml`


## Example Plays

### Setting up a LEMP server

Create the file `group_vars/all`. There is a placeholder `group_vars/all-EXAMPLE` you can use to get started.

Assuming your target system(s) are defined in `/etc/ansible/hosts` you should be able to run:

    ansible-playbook lemp.yml

### Setting up a Wordpress Server

Here's a simple play that builds on the LEMP deployment by customizing Nginx for your domain 
with Wordpress specific caching.

Adjust the parameters for your website in `wordpress.yml` and then:

    ansible-playbook wordpress.yml


## Reference Material

[Ansible Docs](http://www.ansibleworks.com/docs/)  
[Pedantically Commented Playbook (Gist)](https://gist.github.com/andrewwood/7129910)  
