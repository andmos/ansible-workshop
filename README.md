# Ansible workshop

Hands-on workshop which contains a few tasks to help you learn the basics of Ansible for configuration management.

## Ansible terms
* Inventory - A repository for storing server names, ip-addresses, ports, usernames and other variables. In its simplest form a YAML-file.

*  Modules - The workhorses of Ansible. They are used to perform tasks such as; install a package, copy a file, ensure a service is started.

* Playbooks - A Yaml-file which says which hosts contains which roles and utilizes one or more modules to achieve the results.

* Task list - List of tasks which executes modules. Used in playbooks and roles.

* Role - Describes which role a host has. For example a server can contain both the Ubuntu role and apache-webserver role.


## Ansible Resources

These are useful resources which explains Ansible. There is no reason for me to rewrite all that excellent documentation here.

* http://docs.ansible.com Offical documentation
* https://github.com/ansible/ansible-examples Offical Examples

## Tasks

1. Use Ansible to install nginx-webserver. For good measure do it on a couple of servers.
2. 
