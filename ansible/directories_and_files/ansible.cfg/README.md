# Ansible.cfg File

## Table Of Contents

---

## A Sample Configuration
```bash
[defaults]
vault_password_file = .vault.pass
connection = smart
timeout = 60
deprecation_warnings = False
host_key_checking = False
pipelining=True
forks=100
```
***[🔝 Table Of Contents](#table-of-contents)***

### Descriptions


| Command                                         | What it does                                            | When to use it                  |
|-------------------------------------------------|---------------------------------------------------------|---------------------------------|
| `[forks](#a-sample-configuration)`              | Set number of using forks                               | **Sometimes**                   |
| `[host_key_checking](#a-sample-configuration)`  | Test destination server's ssh key is available or not   | **Rarely** - Just for testing   |

***[🔝 Table Of Contents](#table-of-contents)***
