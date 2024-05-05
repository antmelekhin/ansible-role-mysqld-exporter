MySQL Exporter
==============

An Ansible role to install, configure and update [MySQL Exporter](https://github.com/prometheus/mysqld_exporter).

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

- `mysqld_exporter_version` The specific version of MySQL Exporter to download (default: `0.15.1`).
- `mysqld_exporter_archive_name` MySQL Exporter archive name (default: `mysqld_exporter-0.15.1.linux-amd64`).
- `mysqld_exporter_archive_extension` MySQL Exporter archive extension (default: `tar.gz`).
- `mysqld_exporter_download_url` URL to download an archive with MySQL Exporter (default: `https://github.com/prometheus/mysqld_exporter/releases/download/v0.15.1`).
- `mysqld_exporter_user` and `mysqld_exporter_group` Unix username and group (default: `mysqld_exporter`).
- `mysqld_exporter_install_path` Path to MySQL Exporter installation directory (default: `/usr/local/bin`).
- `mysqld_exporter_config_path` Path to MySQL Exporter directory with mysql connection config (default: `/usr/local/etc`).
- `mysqld_exporter_mysql_user` and `mysqld_exporter_mysql_password` `(Required)` Username and password to be used for connecting to MySQL Server (default: `''`).
- `mysqld_exporter_mysql_host` MySQL host (default: `localhost`).
- `mysqld_exporter_mysql_port` MySQL port (default: `3306`).
- `mysqld_exporter_web_listen_address` Address to listen on for web interface and telemetry (default: `0.0.0.0`).
- `mysqld_exporter_web_listen_port` The port to bind to (default: `9104`).
- `mysqld_exporter_web_telemetry_path` The path at which to serve metrics (default: `/metrics`).
- `mysqld_exporter_tls_server_config` Certificate and key files for server to use to authenticate to client.
- `mysqld_exporter_http_server_config` Enable HTTP/2 support. Note that HTTP/2 is only supported with TLS.
- `mysqld_exporter_basic_auth_users` Users and password for basic authentication. Passwords are automatically hashed with bcrypt.
- `mysqld_exporter_collectors` Collectors list (default: `[]`).
- `mysqld_exporter_log_level` MySQL Exporter logging level.

  Available values:
  - `debug`
  - `info` (default)
  - `warn`
  - `error`

- `mysqld_exporter_log_format` Output format of log messages.

  Available values:
  - `logfmt` (default)
  - `json`

Dependencies
------------

None.

Example Playbook
----------------

- Install and configure `MySQL Exporter`. Also, you need to create a user to connect the exporter to a database instance:

  ```yaml
  ---
  - name: 'Setup MySQL Exporter'
    hosts: all
    vars:
      exporter_user_name: 'exporter'
      exporter_user_password: 'Pa$$w0rd'
      db_host: 'localhost'
      db_login_user: 'root'
      db_login_password: '$ecretP4ssword!'

    pre_tasks:
      - name: 'Create mysql user'
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

- Install and configure `MySQL Exporter` with TLS certificate and basic authentication feature.

  ```yaml
  ---
  - name: 'Setup MySQL Exporter'
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
