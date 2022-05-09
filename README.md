# docker-centos9-ansible

[![Build](https://github.com/mghalbi/docker-centos9-ansible/actions/workflows/build.yml/badge.svg)](https://github.com/mghalbi/docker-centos9-ansible/actions/workflows/build.yml)
[![Docker pulls](https://img.shields.io/docker/pulls/mghalbi/docker-centos9-ansible)](https://hub.docker.com/repository/docker/mghalbi/docker-centos9-ansible/)

CentOS 9 Docker container for Ansible playbook and role testing.

## Tags

- `latest`: Latest stable version of Ansible, with Python 3.x.

## How to Build

This image is built on Docker Hub automatically any time the upstream OS container is rebuilt, and any time a commit is made or merged to the `main` branch.

  1. [Install Docker](https://docs.docker.com/engine/installation/).
  2. `cd` into this directory.
  3. Run `docker build -t docker-centos9-ansible/ .`

## How to Use

  1. [Install Docker](https://docs.docker.com/engine/installation/).
  2. Pull this image from Docker Hub: `docker pull mghalbi/docker-centos9-ansible:latest` (or use the image you built earlier, e.g. `centos9-ansible`).
  3. Run a container from the image: `docker run --detach --privileged --volume=/sys/fs/cgroup:/sys/fs/cgroup:ro mghalbi/docker-centos9-ansible:latest` (to test my Ansible roles, I add in a volume mounted from the current working directory with ``--volume=`pwd`:/etc/ansible/roles/role_under_test:ro``).
  4. Use Ansible inside the container:
    a. `docker exec --tty [container_id] env TERM=xterm ansible --version`
    b. `docker exec --tty [container_id] env TERM=xterm ansible-playbook /path/to/ansible/playbook.yml --syntax-check`

## Author

Created in 2022 by [Mohsen Ghalbi](https://mghalbi.github.io/).
