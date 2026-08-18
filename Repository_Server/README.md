# Setting Up Internal Repository Server

## Table Of Contents
- [Install Docker](#install-docker)
- [Configure Authentication On Server](#configure-authentication-on-server)

---

## Install Docker
First install docker on server and client. If need help, take a look at `CHANGEME_PLEASE`.


---

## Configure Authentication On Server
```bash
htpasswd -Bc /PATH_YOU_WANT/htpasswd USER
```

File is located in `/PATH_YOU_WANT/htpasswd`

---

## Create And Configure Compose File
```bash
sudo vim docker-compose.yml
```

Add these:
```bash
version: "3.8"

services:

  registry:
    image: registry:2
    container_name: YOUR_CONTAINER_NAME
    restart: always

    ports:
      - "5000:5000"

    environment:
      REGISTRY_AUTH: htpasswd
      REGISTRY_AUTH_HTPASSWD_REALM: Registry Realm
      REGISTRY_AUTH_HTPASSWD_PATH: /PATH_YOU_WANT/htpasswd

      REGISTRY_STORAGE_FILESYSTEM_ROOTDIRECTORY: /var/lib/registry

    volumes:
      - ./data:/var/lib/registry
      - ./auth:/auth
```

Execute and run your compose file:
```bash
docker compose up -d
docker compose ps           # Must see your created container and running
```

---

## Network And Connectivity Status
Make sure you have connectivity with your repository hos from your clients by commends such as:
```bash
ping IP_ADDRESS                                     # Change `IP_ADDRESS` with your host ip address. Mine is here: 192.168.56.1. You will check connectivity with your host using icmp protocol if it's not blocked by firewall.
curl -IL http://IP_ADDRESS:PORT/VERSION_NUMBER      # Change `IP_ADDRESS` with your host ip address and `PORT` with your host port number and `VERSION_NUMBER` with version of repoitory server. Mine is here: http://192.168.56.1:5000/v2
```

---

## Config Server's Docker Daemon
Config your docker daemon; Here I'm using http (insecure and not recommended):
```bash
cd /etc/docker
vim daemon.json
```

Add/Modify these:
```bash
{"insecure-registries": ["192.168.56.1:5000"]}
```

Restart docker service for applying changes:
```bash
sudo systemctl restart docker
```

Check your connection and login by created user:
```bash
docker login 192.168.56.1:5000
```

---

## Pull And Push Images
* `Push Images:`
Tag your images:
```bash
docker tag nginx:latest 192.168.56.1:5000/nginx:latest
``` 

Push tagged images:
```bash
docker push 192.168.56.1:5000/nginx:latest
```

`Pull Images:`
On client host:
```bash
docker pull 192.168.56.1:5000/nginx:latest
```

Check all images on registery:
```bash
curl -u admin:password http://192.168.56.1:5000/v2/_catalog
```

