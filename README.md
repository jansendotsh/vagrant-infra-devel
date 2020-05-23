# vagrant-infra-devel

## Goal

This is a repository built to store my Vagrant environments for work across several machines. Currently, this only contains a single web development host and a basic creation using an Ansible provisioner. This will grow and be modularized as we proceed. 

## Requirements

- Vagrant
- Ansible (running with Python 3)

## Getting Started

```
vagrant up
ansible-playbook docker.yml -K -i inventory/hosts -e ansible_python_interpreter=/usr/bin/python3
```

## toDo

- Update "Getting Started" instructions & docker.yml file to use role instead of separate item
- Incorporate deployment of data, docker-compose file and starting services
    - Ensure that files have correct contexts on Fedora host:
        - https://www.projectatomic.io/blog/2015/06/using-volumes-with-docker-can-cause-problems-with-selinux/
