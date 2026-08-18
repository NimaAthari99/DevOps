# Installation ansible on Ubuntu

---

## Table Of Contents
- [Installation ansible on Ubuntu](#installation-ansible-on-ubuntu)
- [Table Of Contents](#table-of-contents)
- [Installing Ansible Dependencies](#step-1-installing-ansible-dependencies)
- [Step 2: Configure PPA Repository & Update Repo](#step-2-configure-ppa-repository--update-repo)
- [Step 3: Install Ansible](#step-3-install-ansible--check-installation)

---

Install dependencies and configure Ansible Repository

## Step 1: Installing Ansible Dependencies
Install ansible dependencies by running the following apt command,
```bash
sudo apt install software-properties-common -y
```

***[Table Of Contents](#table-of-contents)***

---

## Step 2: Configure PPA Repository & Update Repo
Once the dependencies are installed then configure PPA repository for ansible, run
```bash
sudo add-apt-repository --yes --update ppa:ansible/ansible
```
Now update repository by running beneath apt command.
```bash
sudo apt update
```

***[Table Of Contents](#table-of-contents)***

---

## Step 3: Install Ansible & Check Installation
Install latest version of ansible
Now we are ready to install latest version of Ansible on Ubuntu 20.04 LTS / 21.04, run following command.
```bash
sudo apt install ansible -y
```

After the successful installation of Ansible, verify its version by executing the command
```bash
ansible --version
```

Great, above output confirms that Ansible version 2.9.6 is installed.

***[Table Of Contents](#table-of-contents)***

