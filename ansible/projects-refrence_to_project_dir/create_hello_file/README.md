# Create Hello File Project

## Table Of Contents
- [Inventory Description](#inventory-description)
    1) [Machines Details](#machines-details)
- [Variables Details](#variables-details)
    1. [Group Variables](#group-variables)
    2. [Host Variables](#host-variables)
- [Roles Directory](#roles-directory)
    1) [create_hello_file Directory](#create_hello_file-directory)
    2) [Defaults Directory](#defaults-directory)
    3) [Tasks Directory](#tasks-directory)
    4) [Templates Directory](#templates-directory)

---

For all projects, first check your configurations are correct and dont have any error. For that, execute this command on your computer and replace your server's IP address with *'YOU_SERVER_IP'*.
```bash
ansible YOU_SERVER_IP -m ping
```

If didnt get any error and output is somthing like image below, your configuration is ok and ready to continue!

---

### Inventory Description
#### Machines Details
File is configured and detailed in **"CHANGE_ME/inventory/README.md"** .

There is 1 group nima_servers. We have 2 machines; **`Hello_VM_1`** and **`Hello_VM_2`**. Because we just want to create a file and open it, we have 2 debian 13 with 1 core and 2GB ram as it is below:

| CPU           | RAM        | STORAGE     |
|---------------|------------|-------------|
| `2 Cores`     | `2 GB`     | `10 GB`     |

***[🔝 Table Of Contents](#table-of-contents)***

---

### Variables Details
#### Group Variables
There are some variables in project which each is using with purpose. For instance, domain name is a variable in main.yml file using for **`hello-group`**. Each variable is described in README.md file of them. Follow we have some links with more details:
- **`CHANGEME/inventory/README.md`**
- **`CHANGEME/inventory/group_vars/README.md`**
- **`CHANGEME/inventory/group_vars/all/README.md`**
- **`CHANGEME/inventory/group_vars/all/create_hello_file/README.md`**
- **`CHANGEME/inventory/group_vars/hello-group/README.md`**

#### Host Variables
Here are variables for all hosts based on each. For example we have name of each machine in hosts.yml file. More detail is available in **`CHANGEME/inventory/README.md`**

***[🔝 Table Of Contents](#table-of-contents)***

---

### Roles Directory
#### create_hello_file Directory
##### Defaults Directory
Here we have 2 files **`hellovm1.yml`** and **`hellovm2.yml`** files. Here is some variable of each host in these files. There is more info described in **`CHANGEME/roles/create_hello_file/defaults/README.md`**

##### Tasks Directory
We have tasks file which want to be executed in project. It's described in **`CHANGEME/roles/create_hello_file/tasks/README.md`**

##### Templates Directory
We put our templates here. In this project, we use this directory just for hello file's name and made it a template.

***[🔝 Table Of Contents](#table-of-contents)***

---

### .vault.pass File
Password Manager.

---

### ansible.cfg File
Ansible main configs are here.

---

### hello_file_creation File
Main project configs we have here.

### Important Note
***Some Projects maay need spectaculer version of ansible. You need to search and find out what version shoud be installed, configured and to be used.***

***[🔝 Table Of Contents](#table-of-contents)***
