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
* https://docs.ansible.com/ansible/modules_by_category.html Very useful index of modules

## To get started

Requirements: Both host and client machines need to have Python version 2 installed. Python Version 3 will _not_ work. The host machine (running ansible) need to be a UNIX-flavour machine. Either Mac OSX or a Linux variant is recommended.

1. Install ansible (homebrew or your package manager of choice)
2. Clone this repository
3. Make sure you can logon with SSH to the server you want to provision.
4. In the inventory file, replace myserver.example.com with your servers IP or domain name.
5. To issue your first ansible command on a remote server, tweak the following command:
```
ansible -i inventory servers --private-key=~/ansible-workshop.pem -u ubuntu --sudo -m ping
```
This command runs the module (-m) ping which just pings the host.

-m module to use, in this case the ping module

-u remote user to log in as.

--sudo use sudo to gain root privileges on the server after logon

--private-key Path to private key used to log on to the server(s)

-i path to the inventory file, followed by which group of servers to connect to.

When the command above works, you can try the example playbook which comes with the project, the playbook uses the default layout from https://docs.ansible.com/ansible/playbooks_best_practices.html#directory-layout.
```
ansible-playbook site.yml -i inventory --private-key=~/ansible-workshop.pem
```

After you have successfully connected I recommend that you use the excellent documentation to solve the next tasks in the workshop. There is no reason to rewrite that documentation here.
