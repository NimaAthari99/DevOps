# Ansible

## Table Of Contents
- [Controller Node](#controller-node)
- [Manage Node](#manage-node)
- [Ansible Directories & Files](#ansible-directories--files)
    * [hosts.yml](#hostsyml)
    * [playbook.yml](#playbookyml)
    * [group_vars](#group_vars)
    * [hot_vars](#hot_vars)
    * [role/vars](#rolevars)
    * [Default Directory](#default-directory)
    * [Files Directory](#files-directory)
    * [Template Directory](#template-directory)
    * [Handler Directory](#handler-directory)
    * [Task Directory](#task-directory)
    * [Vault](#vault)
    * [ansible.cfg](#ansiblecfg)
- [Variables](#variables)
- [Tags](#tags)
- [Roles](#roles)
- [AdHoc Commands](#adhoc-commands)
- 

---

***NOTE:*** IF YOU THINK YOU HAVE A GOOD ANSIBLE CODE AND WANT TO TEST IT, RUN IT TWICE. IF IN SECOND TIME YOU HAD **'OK'** STATE FROM EVERYTHING, IT'S A GOOD ANSIBLE CODE. IF NOT, YOUR CODE CAN GET BETTER! BUT IT DOESN'T MEAN THAT IT IS NOT A GOOD CODE; IT MEANS IT CAN GET BETTER IF YOU WANT. (DON'T PLAY WITH SOMETHING THAT IS GOING RIGHT AND WORKING. CHANGE CURRENT CODE IF YOU CURTAIN IT WILL GET BETTER!)

---

## Controller Node
Which our projects are in it.

***[🔝 Table Of Contents](#table-of-contents)***

---

## Manage Node
Childes of controller node.

***[🔝 Table Of Contents](#table-of-contents)***

---

## Ansible Directories & Files
### hosts.yml
    Where information of hosts is. For example:
        - Server location
        - ansible_host: IP address (Better to use Computer Name)
        - ansible_host: Server Name
        - ansible_port: Port
        - ansible_user: SSH user

In this file we have some groups that each group has some hosts.

***[🔝 Table Of Contents](#table-of-contents)***

---

### playbook.yml
Is in root of project & each playbook has a role, do an action & etc. It means that what will install or widely what action will be done on which server. In playbook we don't have the address of server and we just have a name from it. A sample playbook.yml file is configured in "CHANGE_ME".

***[🔝 Table Of Contents](#table-of-contents)***

---

### group_vars
Variables from groups are here. We can have variable per group. We use when want to just do action specific group of host.

***[🔝 Table Of Contents](#table-of-contents)***

---

### host_vars
Variables from hosts are here. We can have variable per host. We use when want to just do action on a specific host.

***[🔝 Table Of Contents](#table-of-contents)***

---

### role/vars
Variables from roles are here. We can have variable per role.

***[🔝 Table Of Contents](#table-of-contents)***

---

### Default Directory
Here we have default variables from your role.

*Note:* It's better to not set variables for roles and use them for groups or hosts. It's easier to learn and more clear.

***[🔝 Table Of Contents](#table-of-contents)***

---

### Files Directory
If want to transfer a file without any variable. It doesn't have any sub file in it, because our files which we want to transfer to manage nodes will be in this folder.

***[🔝 Table Of Contents](#table-of-contents)***

---

### Template Directory
If want to transfer a file with variable. Exactly like files directory, it doesn't have any sub file in it, because our files which we want to transfer to manage nodes will be in this folder.

***[🔝 Table Of Contents](#table-of-contents)***

---

### Handler Directory
All restarts and changes of services and servers will be in this directory. For instane you have some changes for nginx and configutrations. You have some tasks which after them need to restart nginx. You can do it two ways. First write it in handler and haandler will be for all tasks of configuration which will restarts that service for us. One way is to write a handler and in each step you need to restart just run that handler.

***[🔝 Table Of Contents](#table-of-contents)***

---

### Task Directory
Our action we want to be execued will be in this directory. 

***[🔝 Table Of Contents](#table-of-contents)***

---

### Vault
Vault is a tool which we can put our important and critical information, variables, paasswords and etc. 

***[🔝 Table Of Contents](#table-of-contents)***

---

### ansible.cfg
Try to don't use host_key_checking; Because of security and simplicity. A sample configuration of this file is available in "CHANGE_ME".

***[🔝 Table Of Contents](#table-of-contents)***

---

## Variables
We use variables like below:
```bash
{{ packages }}
```

In "CHANGE_ME" we hve  an example of using variables in ansible files.

***[🔝 Table Of Contents](#table-of-contents)***

---

## Tags
We can run just one specific service using tags. 

***[🔝 Table Of Contents](#table-of-contents)***

---

## Roles
For creating a new role, execute this command in a directory you want:
```bash
ansible-galaxy init YOU_NEW_ROLE
```

Then you can what your changes with command below which will create ansible defaault stracture files and directories for you:
```bash
tree
```

***[🔝 Table Of Contents](#table-of-contents)***

---

## AdHoc Commands
Commands which we run with no playbook. It doesn't have any structure. We use them for some not important  A list of some adhoc command is introduced in "CHANGE_Me".

***[🔝 Table Of Contents](#table-of-contents)***

---

## Some Ansible Commands


---

## Important Note
***Some Projects may need spectaculer version of ansible. You need to search and find out what version shoud be installed, configured and to be used.***

***[🔝 Table Of Contents](#table-of-contents)***

---