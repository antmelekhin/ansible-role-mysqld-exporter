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

- `mysqld_exporter_version` The version of MySQLd Exporter to install (default: `0.15.1`).
- `mysqld_exporter_archive_name` The MySQLd Exporter archive name without an extension (default: `mysqld_exporter-0.15.1.linux-{{ _mysqld_exporter_architecture }}`).
- `mysqld_exporter_download_url` The MySQLd Exporter archive download URL (default: `https://github.com/prometheus/mysqld_exporter/releases/download/v0.15.1`).
- `mysqld_exporter_checksum_url` The MySQLd Exporter checksum file URL (default: `{{ mysqld_exporter_download_url }}/sha256sums.txt`).
- `mysqld_exporter_download_path` Local path to download and extract the archive (default: `/tmp`).
- `mysqld_exporter_user` and `mysqld_exporter_group` System user and group that will be created (default: `mysqld_exporter`).
- `mysqld_exporter_install_path` The MySQLd Exporter installation directory (default: `/usr/local/bin`).
- `mysqld_exporter_config_path` The MySQLd Exporter directory, that contains the MySQL Server connection settings (default: `/etc/mysqld_exporter`).
- `mysqld_exporter_mysqld_user` and `mysqld_exporter_mysqld_password` (`Required`) The target MySQL Server username and password. Please refer to [the official documentation](https://github.com/prometheus/mysqld_exporter#required-grants) for a description of the required grants for a MySQL user.
- `mysqld_exporter_mysqld_host`The target MySQL Server host (default: `''`).
- `mysqld_exporter_mysqld_port` The target MySQL Server port (default: `3306`).
- `mysqld_exporter_mysqld_socket` The target MySQL Server unix socket (default: `/run/mysqld/mysqld.sock`).
- `mysqld_exporter_web_listen_address` The address to listen for the web interface and telemetry (default: `0.0.0.0`).
- `mysqld_exporter_web_listen_port` The port number that MySQLd Exporter listens on (default: `9104`).
- `mysqld_exporter_web_telemetry_path` The path to expose metrics (default: `/metrics`).
- `mysqld_exporter_log_level` The MySQLd Exporter logging level. Supported levels are: `debug`, `info`, `warn`, `error` (default: `info`).
- `mysqld_exporter_log_format` A log message format. Supported formats are: `logfmt`, `json` (default: `logfmt`).
- `mysqld_exporter_tls_server_config` Certificate and key files for server to use to authenticate to client (default: `{}`).
- `mysqld_exporter_http_server_config` Enable HTTP/2 support (default: `{}`). Note that HTTP/2 is only supported with TLS.
- `mysqld_exporter_basic_auth_users` Users and password for basic authentication (default: `{}`). Passwords are automatically hashed with bcrypt.
- `mysqld_exporter_collectors` A list of collectors to use (default: `[]`). See [the official documentation](https://github.com/prometheus/mysqld_exporter#collector-flags) for a list of available collector flags.

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
