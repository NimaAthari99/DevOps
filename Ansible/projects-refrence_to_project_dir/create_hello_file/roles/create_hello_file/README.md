# Roles Folder

## Table Of Contents
- 

---

Here we have all configurations, tasks, handlers and variables for tasks we want to be executed.

### `defaults` Directory
Variables of hole tasks and configurations of project.

#### `hellovm1.yml` File
It's for  hellovm1 variables. More information is available in **`CHANGE_ME/roles/create_hello_files/defaults/README.md`**.

| Variable      | Value         |
|---------------|---------------|
| `sub`         | `hellovm1`    |
| `domain`      | `nima`        |
| `tld`         | `local`       |

#### `hellovm2.yml` File
It's for  hellovm2 variables. More information is available in **`CHANGE_ME/roles/create_hello_file/defaults/README.md`**.

| Variable      | Value         |
|---------------|---------------|
| `sub`         | `hellovm2`    |
| `domain`      | `nima`        |
| `tld`         | `local`       |

***[🔝 Table Of Contents](#table-of-contents)***

---

### `tasks` Directory
It's located in **`CHANGE_MEroles/create_hello_file/tasks`** for executing tasks on hole project. More detail is introduced in **`CHANGE_ME/roles/create_hello_file/tasks/README.md`**.

#### `main.yml` File
There is two tasks in this file for running on hole projec. We could create two files ad have each task in one file. More info about task files is available in **`CHANGE_ME/roles/create_hello_file/tasks/README.md`**.

***[🔝 Table Of Contents](#table-of-contents)***

---

### Create_Hello_File Directory
It's for defining output file name template which has just **`main.yml`** file in this project. All about it is in **`CHANGE_ME/inventory/group_vars/all/create_hello_files/README.md`**.

***[🔝 Table Of Contents](#table-of-contents)***

---

### Hello-Group Directory
Variables in this directory will be affected on hello-group hosts. More information is available in **`CHANGE_ME/inventory/group_vars/all/hello-group/README.md`**.

***[🔝 Table Of Contents](#table-of-contents)***

**[🔝 Back To Top](#defaults-directory)**