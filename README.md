# vagrant-infra-devel

## Goal

This is a repository built to store my Vagrant environments for work across several machines. Currently, this only contains a single web development host and a basic creation using an Ansible provisioner. This will grow and be modularized as we proceed. 

## Requirements

- Vagrant
- Ansible (running with Python 3)

## toDo

- Incorporate deployment of data, docker-compose file and starting services
    - Ensure that files have correct contexts on Fedora host:
        - https://www.projectatomic.io/blog/2015/06/using-volumes-with-docker-can-cause-problems-with-selinux/