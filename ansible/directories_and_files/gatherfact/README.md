# Gatherfact

Will give us variables about computers we want.

## Syntax
```bash
ansible [all/group/host] -i host_file[inventory/hosts.yml] -m setup -a "filter=ansible_os_family"
```
We use **'-m** to use modules and **'-a** to use module's option.

***Example 1:***
```bash
ansible localhost -m setup
```
It will shows all variables and information about localhost.

***Example 2:***
```bash
ansible nginx_servers -i inventory/hosts.yml -m setup -a "filter=ansible_os_family"
```
It will shows operating system type of servers in nginx_servers group.

## Some Filters

| Filter                           | Description                      |
|----------------------------------|----------------------------------|
| `ansible_all_ipv4_addresses`     | `Shows IP Addresses`             |
| `ansible_hostname`               | `Shows Hostname`                 |
| `ansible_os_family`              | `Shows System OS`                |
| `ansible_mounts`                 | `Mount Points`                   |

***[🔝 Table Of Contents](#table-of-contents)***
