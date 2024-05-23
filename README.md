MySQLd Exporter
===============

An Ansible role to install, configure and update the [MySQLd Exporter](https://github.com/prometheus/mysqld_exporter).

Requirements
------------

- Supported version of Ansible: 2.12 and highter.
- `gnu-tar` on Mac as deployer host (`brew install gnu-tar`).
- `passlib` on a deployer host when using the basic authentication feature (`python3 -m pip install passlib[bcrypt]`).
- `cryptography` or `pyOpenSSL` on a deployer host when using the TLS feature.
- Supported platforms:
  - Amazon Linux
    - 2023
  - Debian
    - 10
    - 11
    - 12
  - RHEL
    - 7
    - 8
    - 9
  - Ubuntu
    - 18.04
    - 20.04
    - 22.04

Role Variables
--------------

All variables that can be overridden are stored in the [defaults/main.yml](defaults/main.yml) file.
Please refer to the [meta/argument_specs.yml](meta/argument_specs.yml) file for a description of the available variables.

Dependencies
------------

None.

Example Playbook
----------------

Install and configure the `MySQLd Exporter`. Also, you need to create a user to connect the `MySQLd Exporter` to a database instance:

```yaml
---
- name: 'Setup the MySQLd Exporter'
  hosts: all
  vars:
    exporter_user_name: 'exporter'
    exporter_user_password: 'Pa$$w0rd'
    db_host: 'localhost'
    db_login_user: 'root'
    db_login_password: '$ecretP4ssword!'

  pre_tasks:
    - name: 'Create a mysql user'
      mysql_user:
        name: '{{ exporter_user_name }}'
        password: '{{ exporter_user_password }}'
        host: '{{ db_host }}'
        priv: '*.*:SELECT,PROCESS,REPLICATION CLIENT'
        login_user: '{{ db_login_user }}'
        login_password: '{{ db_login_password }}'
        state: present

  roles:
    - role: antmelekhin.mysqld_exporter
      mysqld_exporter_mysql_user: '{{ exporter_user_name }}'
      mysqld_exporter_mysql_password: '{{ exporter_user_password }}'
```

Install and configure the `MySQLd Exporter` with TLS certificate and basic authentication feature.

```yaml
---
- name: 'Setup the MySQLd Exporter'
  hosts: all
  roles:
    - role: antmelekhin.mysqld_exporter
      mysqld_exporter_mysql_user: 'exporter'
      mysqld_exporter_mysql_password: 'Pa$$w0rd'
      mysqld_exporter_tls_server_config:
        cert_file: '/etc/ssl/certs/mysqld_exporter.cert'
        key_file: '/etc/ssl/private/mysqld_exporter.key'
      mysqld_exporter_basic_auth_users:
        newuser1: newpassword1
        newuser2: newpassword2
```

License
-------

MIT

Author Information
------------------

Melekhin Anton.
