# Inventory Folder

## Table Of Contents
- [hosts.yml File Description](#hostsyml-file-description)
- [Group_Vars Directory](#group_vars-directory)
- [All Directory](#all-directory)
- [Create_Hello_File Directory](#create_hello_file-directory)
- [Hello-Group Directory](#hello-group-directory)

---

There is 1 group hello-group. We have 2 machines; **`hellovm1`** and **`hellovm2`**. Because we just want to create a file and open it, we have 2 debian 13 with 1 core and 2GB ram as it is below:

| CPU           | RAM        | STORAGE     |
|---------------|------------|-------------|
| `1 Core`      | `2 GB`     | `20 GB`     |


### hosts.yml File Description
Variables of each host is in this file.

**`hellovm1.nima.local`** variables:
| Variable          | Value             |
|-------------------|-------------------|
| `ansible_host`    | `192.168.56.13`   |
| `ansible_user`    | `nimaathari`      |
| `ansible_port`    | `22`              |
| `MAIN_USER`       | `Nima Athari`     |

**`hellovm2.nima.local`** variables:
| Variable          | Value             |
|-------------------|-------------------|
| `ansible_host`    | `192.168.56.14`   |
| `ansible_user`    | `nimaathari`      |
| `ansible_port`    | `22`              |

***[🔝 Table Of Contents](#table-of-contents)***

---

### Group_Vars Directory
This directory is for defining variables which will affect on group hosts. More detail is written in **`CHANGE_ME/inventory/group_vars/README.md`**.

***[🔝 Table Of Contents](#table-of-contents)***

---

### All Directory
This directory is located in **`CHANGE_ME/inventory/group_vars/all`** for defining variables which will affect on all groups and hosts. More detail is introduced in **`CHANGE_ME/inventory/group_vars/all/README.md`**.

***[🔝 Table Of Contents](#table-of-contents)***

---

### Create_Hello_File Directory
It's for defining output file name template which has just **`main.yml`** file in this project. All about it is in **`CHANGE_ME/inventory/group_vars/all/create_hello_files/README.md`**.

***[🔝 Table Of Contents](#table-of-contents)***

---

### Hello-Group Directory
Variables in this directory will be affected on hello-group hosts. More information is available in **`CHANGE_ME/inventory/group_vars/all/hello-group/README.md`**.

***[🔝 Table Of Contents](#table-of-contents)***