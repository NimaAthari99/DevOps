# Projects

## Table Of Contents
- [](#create_hello_file)
- [](#web-db-practice)
- []()

---

For all projects, first check your configurations are correct and dont have any error. For that, execute this commaand on your computer and replace your server's IP address with *'YOU_SERVER_IP'*.
```bash
ansible YOU_SERVER_IP -m ping
```

If didn't get any error and output is somthing like image below, your configuration is ok and ready to continue!
img

---

## Create_Hello_File
A basic and level zero project for leaning basic ansible structure. Here we have 2 hosts. 

This ansible code will first check weather **`Desktop`** directory is available or not; If available, will continue progreesion; However if not, will create Desktop directory. Then will create **`Hello_File`**. Then it will append a messege to that file which is described in project. 

NOT_COMPLETE

---

## WEB-DB-Practice
Setting up 2 nginx servers & 2 apache servers & 1 sql server vagrant machines using ansible and config them by ansible configuration file path:"https://github.com/NimaAthari99/Linux/blob/main/ansible/projects/Ansible-VM/Vagrantfile" . Configuration instruction is available in my github in "https://github.com/NimaAthari99/Linux/tree/main/ansible/projects/web-db-practice"

### Inventory Description
#### Machines details
File is configured and detailed in "https://github.com/NimaAthari99/Linux/blob/main/ansible/projects/web-db-practice/inventory/hosts.yml" .

As it's clarify, there are 3 groups nginx_servers, apache_servers & sql_servers. We have 5 machines which just two of them are going to get up. 

### Variables details
#### Group variables
There are some variables in project. "packages" which is located in "https://github.com/NimaAthari99/Linux/blob/main/ansible/projects/web-db-practice/inventory/group_vars/all/packages.yml" , are used for all 3 machine groups. Have 2  other variables called "certs" & "domain" located in "https://github.com/NimaAthari99/Linux/tree/main/ansible/projects/web-db-practice/inventory/group_vars/web_servers" . 

### Host variables
Here are variables for all hosts based on each. For example we have name of each machine in hosts.yml .

NOT_COMPLETE

---

# Important Note
***Some Projects may need spectaculer version of ansible. You need to search and find out what version shoud be installed, configured and to be used.***