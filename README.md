MySQL Exporter
==============

An Ansible role for install, configure and update [MySQL Exporter](https://github.com/prometheus/mysqld_exporter).

Requirements
------------

- Supported version of Ansible: 2.9 and highter.
- `gnu-tar` on Mac as deployer host (`brew install gnu-tar`).
- Supported platforms:
  - RHEL
    - 7
    - 8
  - Ubuntu
    - 20.04
    - 22.04
  - Debian
    - 10
    - 11

Используемые переменные
-----------------------

- `mysqld_exporter_version` The specific version of MySQL Exporter to download (default: `0.14.0`).
- `mysqld_exporter_package_name` MySQL Exporter archive name.
- `mysqld_exporter_archive_extension` MySQL Exporter archive extension (default: `tar.gz`).
- `mysqld_exporter_download_url` URL to download an archive with MySQL Exporter.
- `mysqld_exporter_user` and `mysqld_exporter_group` Unix username and group (default: `mysqld_exporter`).
- `mysqld_exporter_install_path` Path to MySQL Exporter installation directory (default: `/usr/local/bin`).
- `mysqld_exporter_config_path` Path to MySQL Exporter directory with mysql connection config (default: `/usr/local/etc`).
- `mysqld_exporter_mysql_user` and `mysqld_exporter_mysql_password` `(Required)` MySQL username and password (default: `''`).
- `mysqld_exporter_mysql_host` MySQL host (default: `localhost`).
- `mysqld_exporter_mysql_port` MySQL port (default: `3306`).
- `mysqld_exporter_web_listen_address` Address to listen on for web interface and telemetry (default: `0.0.0.0`).
- `mysqld_exporter_web_listen_port` The port to bind to (default: `9104`).
- `mysqld_exporter_web_telemetry_path` The path at which to serve metrics (default: `/metrics`).
- `mysqld_exporter_log_level` MySQL Exporter logging level (default: `info`).
- `mysqld_exporter_collect` Collectors list (default: `[]`).

Dependencies
------------

None.

Example Playbook
----------------

- Install and configure `MySQL Exporter`:

  ```yaml
  ---
  - name: 'Setup MySQL Exporter'
    hosts: all
    roles:
      - role: ansible-role-mysqld-exporter
        mysqld_exporter_mysql_user: 'exporter'
        mysqld_exporter_mysql_password: 'Pa$$word'
  ```

License
-------

MIT

Author Information
------------------

Melekhin Anton.
