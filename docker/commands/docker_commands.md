# Some Docker Commands

## Table Of Contents
- [Basic Commands](#basic-commands)

---

## Basic Commands

| Command                                                                                                           | What it does                                          |
|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------|
| `docker version`                                                                                                  | Shows docker installed details                        |
| `docker images`                                                                                                   | Shows active docker images                            |
| `docker image load -i FILE.tar`                                                                                   | Shows active docker images                            |
| `docker image rm IMAGE`                                                                                           | Shows active docker images                            |
| `docker compose ps`                                                                                               |                                                       |
| `docker compose ps -a`                                                                                            |                                                       |
| `docker compose images`                                                                                           |                                                       |
| `docker compose build`                                                                                            |                                                       |
| `docker compose up`                                                                                               |                                                       |
| `docker compose up -d`                                                                                            |                                                       |
| `docker compose up --force-recreate COONTAINER_NAME`                                                              |                                                       |
| `docker compose down`                                                                                             |                                                       |
| `docker compose down --remove-orphans`                                                                            |                                                       |
| `docker compose logs`                                                                                             |                                                       |
| `docker compose logs COONTAINER_NAME --tail=100`                                                                  |                                                       |
| `docker compose exec`                                                                                             |                                                       |  
| `docker compose scale`                                                                                            |                                                       |
| `docker logs SERVICE_NAME `                                                                                       |                                                       |
| `docker rm -f SERVICE_NAME `                                                                                      |                                                       |
| `docker run -d --name mysql -e MYSQL_ROOT_PASSWORD=*P@SSW0RD mysql:5.7`                                           |                                                       |
| `docker run –d --name mysql_container -v mysql_data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=*P@SSW0RD mysql:57`     |                                                       |
| `docker exec -it *mysql bash`                                                                                     |                                                       |
| `docker volume ls `                                                                                               |                                                       |
| `docker volume inspect *mysql_data  `                                                                             |                                                       |
| `docker tag registry.gitlab.com/user/project:latest registry.gitlab.com/newuser/newrepo:newtag `                  |                                                       |
| `docker network create *elk_net`                                                                                  |                                                       |
| `docker network create web_net -o com.docker.network.bridge.name=web_net`                                         |                                                       |
| `dcker save -o DESTINATION.tar PATH_TO_IMAGE/IMAGE:VERSION`                                                       | Save docker image as a `.tar` file                    |
| `docker load -i DESTINATION.tar`                                                                                  | Loads image from `.tar` file                          |
| `docker login registry.gitlab.com`                                                                                | Login by docker user                                  |
| `docker push SERVER_ADDRESS/PATH/IMAGE:VERSION`                                                                   | Save image in `SERVER_ADDRESS/PATH/IMAGE:VERSION`     |



***[🔝 Table Of Contents](#table-of-contents)***

---