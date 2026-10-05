# Some Docker Commands

## Table Of Contents

- [Basic Commands](#basic-commands)
- [Docker Image](#docker-image)
- [Docker Compose](#docker-compose)
- [Docker Volume](#docker-volume)
- [Docker Network](#docker-network)

---

## Basic Commands

| Command                                                                                                           | What it does                                                          |
|-------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| `docker version`                                                                                                  | Shows docker installed details                                        |
| `docker logs SERVICE_NAME`                                                                                        | Show SERVICE_NAME logs                                                |
| `docker rm -f SERVICE_NAME`                                                                                       |                                                                       |
| `docker run -d --name mysql -e MYSQL_ROOT_PASSWORD=*P@SSW0RD mysql:5.7`                                           |                                                                       |
| `docker run –d --name mysql_container -v mysql_data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=*P@SSW0RD mysql:57`     |                                                                       |
| `docker exec -it *mysql bash`                                                                                     |                                                                       |
| `docker run -itd --name *COONTAINER_NAME --hostnme *COONTAINER_NAME *busybox`                                     | Will create a container named COONTAINER_NAME with busybox image      |
| `docker tag registry.gitlab.com/user/project:latest registry.gitlab.com/newuser/newrepo:newtag`                   |                                                                       |
| `dcker save -o DESTINATION.tar PATH_TO_IMAGE/IMAGE:VERSION`                                                       | Save docker image as a `.tar` file                                    |
| `docker load -i DESTINATION.tar`                                                                                  | Loads image from `.tar` file                                          |
| `docker login registry.gitlab.com`                                                                                | Login by docker user                                                  |
| `docker push SERVER_ADDRESS/PATH/IMAGE:VERSION`                                                                   | Save image in `SERVER_ADDRESS/PATH/IMAGE:VERSION`                     |

***[🔝 Table Of Contents](#table-of-contents)***

---

### Docker Image

| Command                                                                                                           | What it does                                                          |
|-------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| `docker images`                                                                                                   | Shows docker images                                                   |
| `docker image load -i FILE.tar`                                                                                   | Load image from a .tar file                                           |
| `docker image rm IMAGE`                                                                                           | Remove docker image                                                   |

***[🔝 Table Of Contents](#table-of-contents)***

---

### Docker Compose

| Command                                                                                                           | What it does                                                          |
|-------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| `docker compose ls`                                                                                               | Show docker compose file location                                     |
| `docker compose ps`                                                                                               | Show docker containers status                                         |
| `docker compose ps -a`                                                                                            | Show docker containers status                                         |
| `docker compose images`                                                                                           | Shows docker images                                                   |
| `docker compose build`                                                                                            | Build compose file                                                    |
| `docker compose up`                                                                                               | Start creating container with compose file                            |
| `docker compose up -d`                                                                                            | Start creating container with compose file                            |
| `docker compose up --force-recreate *COONTAINER_NAME`                                                             | Start creating container with compose file and recreate container     |
| `docker compose down`                                                                                             | Stop running container                                                |
| `docker compose down -V`                                                                                          | Stop running container and remove container volume                    |
| `docker compose down --remove-orphans`                                                                            |                                                                       |
| `docker compose logs`                                                                                             | Show logs                                                             |
| `docker compose logs *COONTAINER_NAME --tail=100`                                                                 | Show COONTAINER_NAME logs                                             |
| `docker compose exec`                                                                                             |                                                                       |  
| `docker compose scale`                                                                                            |                                                                       |

***[🔝 Table Of Contents](#table-of-contents)***

---

### Docker Volume

| Command                                                                                                           | What it does                                                          |
|-------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| `docker volume ls`                                                                                                | Shows docker volumes                                                  |
| `docker volume inspect *mysql_data`                                                                               | Show mysql_data volume details                                        |

***[🔝 Table Of Contents](#table-of-contents)***

---

### Docker Network

| Command                                                                                                           | What it does                                                          |
|-------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| `docker network create *elk_net`                                                                                  | Create web_net docker network                                         |
| `docker network create *web_net -o com.docker.network.bridge.name=*web_net`                                       | Create web_net docker network                                         |

***[🔝 Table Of Contents](#table-of-contents)***

---
