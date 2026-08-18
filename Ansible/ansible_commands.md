# Some Ansible Commands

## Table Of Contents
- [Ansible Commands](#ansible-commands)

---

## Ansible Commands

| Command                                                                                   | What it does                                  |
|-------------------------------------------------------------------------------------------|-----------------------------------------------|
| `ansible -i inventory/host.yaml all -m ping`                                              | Get pong response from all defined hosts      |
| `ansible-playbook -i hosts.yaml /PATH_TO_PLAYBOOK/PLAYBOOK.yml`                           | Run your playbook file                        |
| `ansible-playbook -i hosts.yaml /PATH_TO_PLAYBOOK/PLAYBOOK.yml --ask-become-pass`         | Ask sudo password if needed                   |
| `ansible-playbook -i hosts.yaml /PATH_TO_PLAYBOOK/PLAYBOOK.yml --list-servers`            | List hosts which playbook will execute on     |
| `ansible-playbook -i hosts.yaml /PATH_TO_PLAYBOOK/PLAYBOOK.yml --list-tags`               | Tags which playbook will execute them         |
| `ansible-playbook -i hosts.yaml --limit=tools-server /PATH_TO_PLAYBOOK/PLAYBOOK.yml`      | Will execute on just `tools-server` host      |
| `ansible-playbook -i hosts.yaml /PATH_TO_PLAYBOOK/PLAYBOOK.yml --tags=set_apt_mirror`     | Will run just `set_apt_mirror` tags           |
| `ansible-playbook -i hosts.yaml /PATH_TO_PLAYBOOK/PLAYBOOK.yml --ask-vault-pass`          | Ask vault password                            |

***[🔝 Table Of Contents](#table-of-contents)***

---