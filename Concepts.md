# Some DevOps Concepts

## Git (Version Control)

- Config
- Status
- Init
- Log
- Clone
- Remote
- Branch
- Switch
- Add
- Commit
- Tag
- Pull
- Push
- Rebase
- Reset
- Revert
- Merge

## GitLab

## GitHub

- Pipeline
- CI/CD

## Jenkins

## Automation

### Ansible

### Ansible AWX

## Containerization

### Docker

- Linux Container
- Containers
- Go Language Base
- Build/Test/Deploy
- CI/CD Support
- Kubernetes Support
- Workspace
- Namespace
- Iolation
- CGroup (Control Group): Gives limitation on resources
- Union FS: Layering, Copy On Write, Caching, Diffing
- Container Format
- Container Daemon
- Rest API
- Docker Client: Where docker cli will execute on.
- Docker Engine
- Docker Host: Docker daemon is installed on it
- Registry: Docker images will store here
- Docker Image: Is bundeled with all dependencies and its ReadOnly.
- Docker Container
- Docker Tool Box
- Docker Deskop
- Docker Compose
- Docker Swarm
- Docker Machine
- Portainer: Docker GUI
- Kithematic: Docker GUI
- Registry Mirror: Nexus
- Ephemeral Contaainers
- Docker Volume
- DNS
- Port Forward
- Docker Network: Bridge/None/Host/Overlay/MacVlan
- Expose Port: Exposed port on container
- Publish Port: Published port on host
- .dockerignore File
- Docker File:
    - ARG                               # Will define some argument
    - FROM                              # Will choose our base image
    - MAINTAINER                        # Will show us who is the owner of file
    - RUN                               # For executing commands in process of creating our image (in image level)
    - CMD (OR ENTRYPOINT)               # For executing commands whrn image is converted to an image (in container level)
    - EXPOSE                            # As a metadata, show us ports are being used in a container
    - ENV                               # Can deffine environment variables
    - COPY                              # Copy a file from host
    - ADD                               # Copy a file from host or url to image
    - VOLUME                            # Destination of image data
    - USER                              # Execution user
    - WORKIDIR                          # Sets working directory
    - STOPSIGNAL                        # Defines container kill signal
    - SHELL                             # Defines shell using
    - HEALTHCHECK                       # Checking  health of image
    - ONBUILD
- Multi Stage Docker File (Build)

## Orchestration

### Kubernetes (Kube | K8S)

### Docker Swarm

## Test

- Unit Test: Test each unit
- Integration Test
- Smoke Test
- Functional Test
- Load Test
- Volume Test
- Stress Test
- End to End Test: 0 to 100 test
- Fast-Fail
