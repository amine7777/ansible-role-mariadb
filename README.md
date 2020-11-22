Ansible role: Terraform
=========

This role helps you to install mariadb on your linux machine.


|Travis|GitHubActions|Quality|Downloads|Version|
|------|-------------|-------|---------|-------|
|[![travis](https://travis-ci.com/amine7777/ansible-role-mariadb.svg?branch=master)](https://travis-ci.com/amine7777/ansible-role-mariadb)|[![github](https://github.com/amine7777/ansible-role-mariadb/workflows/CI/badge.svg)](https://github.com/amine7777/ansible-role-mariadb/actions)|[![quality](https://img.shields.io/ansible/quality/50498)](https://galaxy.ansible.com/amine7777/mariadb)|[![downloads](https://img.shields.io/ansible/role/d/50498)](https://galaxy.ansible.com/amine7777/mariadb)|[![Version](https://img.shields.io/github/release/amine7777/ansible-role-mariadb.svg)](https://github.com/amine7777/ansible-role-mariadb/releases/)|

![](mariadb.jpg)

Requirements
------------
- Linux machine
- Ansible 2.10

Role Variables
--------------
These variables helps to manage mariadb installation.

You can specify your mariadb version in this variable.
```yaml
mariadb_version: 0.13.1
mariadb_arch: amd64
mariadb_directory_path: /usr/local/bin
```
This is the url where mariadb will be downloaded.
```yaml
mariadb_download_url: 'https://releases.hashicorp.com/mariadb/{{ mariadb_version }}/mariadb_{{ mariadb_version }}_linux_{{ mariadb_arch }}.zip'
```
This is the path where packer binary will be stored.
```yaml
mariadb_directory_path: /usr/local/bin
```

Example Playbook
----------------

```yaml
- hosts: all
  roles:
     - amine7777.mariadb
```


Author Information
------------------

- [Amine Kahlaoui](https://github.com/amine7777), DevOps engineer.
