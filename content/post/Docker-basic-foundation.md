---
title: Docker basic foundation
date: 2018-02-18 16:35:32
tags:
- Docker
---

Base on CentOS 7, Docker 1.12.6 

# Install Docker

Some pre-requirment to install Docker to a Linux OS.

  - Docker only can be installed on a 64 bit OS.
  - Kernel version over 3.10 is recommended. recommend
  - Need to enable cgroup and namespace.

Now it is easier to install Docker in CentOS or Fedora, it can be searched by
`yum` command like below:

```
# yum search docker | grep ^docker
docker-client.x86_64 : Client side files for Docker
docker-client-latest.x86_64 : Client side files for Docker
docker-common.x86_64 : Common files for docker and docker-latest
docker-compose.noarch : Multi-container orchestration for Docker
docker-distribution.x86_64 : Docker toolset to pack, ship, store, and deliver
docker-latest-logrotate.x86_64 : cron job to run logrotate on Docker containers
docker-latest-v1.10-migrator.x86_64 : Calculates SHA256 checksums for docker
docker-logrotate.x86_64 : cron job to run logrotate on Docker containers
docker-lvm-plugin.x86_64 : Docker volume driver for lvm volumes
docker-python.x86_64 : An API client for docker written in Python
docker-registry.x86_64 : Registry server for Docker
docker-v1.10-migrator.x86_64 : Calculates SHA256 checksums for docker layer
docker.x86_64 : Automates deployment of containerized applications
docker-devel.x86_64 : A golang registry for global request variables (source
docker-forward-journald.x86_64 : Forward stdin to journald
docker-latest.x86_64 : Automates deployment of containerized applications
docker-novolume-plugin.x86_64 : Block container starts with local volumes
docker-unit-test.x86_64 : Automates deployment of containerized applications -
```

Running `yum -y install docker` to install docker to your system. 

```
# yum -y install docker

...snip...

Installed:
  docker.x86_64 2:1.12.6-71.git3e8e77d.el7.centos.1                                                                                                                      

Complete!

```
After the installation, start docker service and run `docker version` to confirm your setup.

```
# systemctl start docker

# docker version
Client:
 Version:         1.12.6
 API version:     1.24
 Package version: docker-1.12.6-71.git3e8e77d.el7.centos.1.x86_64
 Go version:      go1.8.3
 Git commit:      3e8e77d/1.12.6
 Built:           Tue Jan 30 09:17:00 2018
 OS/Arch:         linux/amd64

Server:
 Version:         1.12.6
 API version:     1.24
 Package version: docker-1.12.6-71.git3e8e77d.el7.centos.1.x86_64
 Go version:      go1.8.3
 Git commit:      3e8e77d/1.12.6
 Built:           Tue Jan 30 09:17:00 2018
 OS/Arch:         linux/amd64
```

# Basic docker command
Here will introduce some basic command to use docker, for more detail please refer (Docker Documentation)[https://docs.docker.com/engine/reference/commandline/docker/].

Docker command will help you to communicate with docker daemon. The docker
daemon will listen and execute docker command. run `docker` or `docker --help` to
get the command list.

```
# docker --help
...
Commands:
    attach    Attach to a running container
    build     Build an image from a Dockerfile
    commit    Create a new image from a container's changes
    ...
    version   Show the Docker version information
    volume    Manage Docker volumes
    wait      Block until a container stops, then print its exit code

Run 'docker COMMAND --help' for more information on a command.
```

Running docker command needs root permission.
