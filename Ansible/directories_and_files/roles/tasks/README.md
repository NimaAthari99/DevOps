# Tasks Main File

## Table Of Contents
- [A Sample Configuration](#a-sample-configuration)
- [Configuration Descriptions](#configuration-descriptions)

---

## A Sample Configuration
```bash
- name: "apt-get update"
  apt:
    update_cache: yes
    cache_valid_time: 3600

- name: Install tools
  apt:
    name: "{{ item }}"
    state: present
  with_items: "{{ packages }}"
  tags: install_packages

- name: ensure nginx is at the latest version
  apt: name=nginx state=latest
  tags: install_nginx

- name: delete default nginx site
  file:
    path: /etc/nginx/sites-enabled/default
    state: absent
  notify: restart nginx
  tags: configure_nginx

- name: copy nginx site.conf
  template:
    src: site.conf.j2
    dest: /etc/nginx/conf.d/{{ domain }}.conf
    owner: root
    group: root
    mode: '0644'
  notify: restart nginx
  tags: configure_nginx

- name: start nginx
  service:
    name: nginx
    state: started
  tags: configure_nginx
```

***[🔝 Table Of Contents](#table-of-contents)***

---

## Configuration Descriptions
This sample configuration has 6 tasks to run. 

### Task 1: apt-get update
```bash
- name: "apt-get update"
  apt:
    update_cache: yes
    cache_valid_time: 3600
```
First task's name is **'apt-get update'**. It uses **'apt'** module to **'update_cache'** for **'3600s'**.

***[🔝 Table Of Contents](#table-of-contents)***

---






***[🔝 Table Of Contents](#table-of-contents)***
