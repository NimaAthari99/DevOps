# All Hosts Group

There is 1 group hello-group. We have 2 machines; **`hellovm1`** and **`hellovm2`**. We can use these groups in our ansible playbooks commmands and add-hoc commands:
- all: Will affect on all hosts and groups.
- children: Will affect on every child host.
- hello-group: Will affect on hosts in only this group means **`hellovm1`** and **`hellovm2`**.
- hosts: Will affect on all child hosts.

Actually this directory is created for variables which will affect on all hosts and groups.

---

### Create_Hello_File Directory
It's for defining output file name template which has just **`main.yml`** file in this project. 

#### Main.yml File Description
```bash
output_filename: hello_{{ inventory_hostname }}.txt
```

This variable is  using for making a naming format template. **`inventory_hostname`** is client's(destination) hostname. For example in our scenario, we have two hosts with **`hellovm1`** and **`hellovm2`** names. The files which are going to be created will be **`hello_hellovm1.nima.local`** and **`hello_hellovm2.nima.local`** :

| Host                      | Created File Name             | 
|---------------------------|-------------------------------|
| `hellovm1.nima.local`     | hello_hellovm1.nima.local     |
| `hellovm2.nima.local`     | hello_hellovm2.nima.local     |
