# Andrew Wood's Ansible Playbooks

This is a set of Ansible playbooks for provisioning and configuring various
CentOS application servers.


## Getting Started

Reference:  
[http://www.ansibleworks.com/docs/intro_installation.html](http://)


## Example Plays

### Setting up a LEMP server

1. Set up your ssh hosts file `~/.ssh/config` so it includes the server(s) you wish to configure.

2. Create your Ansible hosts file (refer to [Ansible docs](http://www.ansibleworks.com/docs/intro_installation.html)). 

3. Create the file `group_vars/all`. There is a placeholder `group_vars/all-EXAMPLE` you can use to get started.

4. Assuming your target system(s) are defined in `/etc/ansible/hosts` you should be able to run:

         ansible-playbook lemp.yml
         
         
   Note: you can also specify a hosts file, it does not need to reside in `/etc/ansible`. For example, I like to use different host files for production and test servers. Example:

         ansible-playbook -i prod lemp.yml
         
