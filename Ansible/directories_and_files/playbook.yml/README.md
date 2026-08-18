# Playbook.yml File

## Table Of Contents
- [Playbook.yml File](#playbookyml-file)
- [Sample Configuration](#sample-configuration)
- [Configuration Descriptions](#configuration-descriptions)
  1. [hosts: nginx_servers](#hosts-nginx_servers)
  2. [become: true](#become-true)
  3. [name: setup nginx web server](#name-setup-nginx-web-server)
  4. [roles:](#roles)
  5. [-{role:nginx,become:True,tags:setup_nginx}](#---role-nginx-become-true-tags-setup_nginx-)

---

## Sample Configuration
```bash
- hosts: nginx_servers
  # Gain Root Access
  become: true
  gather_facts: yes
  name: setup nginx web server
  roles:
  # Install & Configure Nginx Service
    - { role: nginx, become: True, tags: setup_nginx }
```
***[🔝 Table Of Contents](#table-of-contents)***

---

## Configuration Descriptions
### hosts: nginx_servers
Configurations will affect on nginx_servers.

### become: true
You have root access when SSH to servers.

### name: setup nginx web server
Name of playbook.

### roles:
Will execute roles we want and tell it in next line.

### - { role: nginx, become: True, tags: setup_nginx }
We said that goto wnginx_servers and in nginx role,  wil root access, do whatever has setup_nginx tag.

***Important Note:*** **You can use tasks instead of roles in playbook file.**

***[🔝 Table Of Contents](#table-of-contents)***

---

## Execute Configurations In Playbook.yml
Execute command below to run our ansible configuration on destintion computers:
```bash
ansible-playbook -i inventory/hosts.yml setup-nginx.yml
```

It uses **'ansible-playbook'** to run our **'setup-nginx'** playbook on hosts in **'inventory/hosts.yml'** file.

***[🔝 Table Of Contents](#table-of-contents)***
