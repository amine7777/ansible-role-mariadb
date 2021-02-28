Ansible role: Terraform
=========

This role helps you to install mariadb on your linux machine.


|Travis|GitHubActions|Quality|Downloads|Version|
|------|-------------|-------|---------|-------|
|[![travis](https://travis-ci.com/amine7777/ansible-role-mariadb.svg?branch=master)](https://travis-ci.com/amine7777/ansible-role-mariadb)|[![github](https://github.com/amine7777/ansible-role-mariadb/workflows/CI/badge.svg)](https://github.com/amine7777/ansible-role-mariadb/actions)|[![quality](https://img.shields.io/ansible/quality/52042)](https://galaxy.ansible.com/amine7777/mariadb)|[![downloads](https://img.shields.io/ansible/role/d/52042)](https://galaxy.ansible.com/amine7777/mariadb)|[![Version](https://img.shields.io/github/release/amine7777/ansible-role-mariadb.svg)](https://github.com/amine7777/ansible-role-mariadb/releases/)|

![](mariadb.jpg)

Requirements
------------
- Linux machine
- Ansible 2.10

Role Variables
--------------
These variables help you to manage mariadb installation.

You can specify your mariadb root password in this variable.
```yaml
mariadb_root_password: changemeplease
```
By setting the root password you can create users using ***mariadb_users*** list.
Here you add users with privilleges to databases or tables.
```yaml
mariadb_users:
  - name: john
    password: doe
    host: localhost
    priv: "mydatabase.*:ALL"
    state: present

  - name: jess
    password: doe
    host: localhost
    priv: "*.*:ALL"
    state: present
```
After settings the users you can create the databases with the appropriate users.
```yaml
mariadb_databases:
  - name: mydatabase
    login_user: john
    login_password: doe
    state: present

  - name: mydatabase
    login_user: jess
    login_password: doet
    state: present
```

Example Playbook
----------------

```yaml
- hosts: all
  vars:
    mariadb_users:
      - name: john
        password: doe
        host: localhost
        priv: "mydatabase.*:ALL"
        state: present

    mariadb_databases:
      - name: mydatabase
        login_user: john
        login_password: doe
        state: present
  roles:
     - amine7777.mariadb
```

Author Information
------------------

- [Amine Kahlaoui](https://github.com/amine7777), DevOps engineer.
