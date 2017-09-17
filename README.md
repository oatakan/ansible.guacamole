guacamole-ansible-role
======================

Ansible role to install and configure guacamole with mariadb, self signed ssl cert and nginx reverse proxy.

Requirements
------------
* centos/rhel 7
* ansible >= 2.2
* selinux disabled

Installation
------------
```shell
ansible-galaxy install joe-speedboat.mariadb
ansible-galaxy install joe-speedboat.guacamole
vi tests/install_guacamole.yml
ansible-playbook tests/install_guacamole.yml
```

Example Playbook
----------------
* `tests/install_guacamole.yml`: Real life example

Role Variables
--------------
* check `defaults/main.yml` for complete list
Some variables that require review:
* `guacamole_version`: 0.9.13-incubating
* `guacamole_mysql_db_password`: .change-this
* `guacamole_mysql_root_password`: .change-that
* `nginx_ssl_reverse_proxy`: true
* `nginx_reverse_proxy_path`: rdp


Usage
-----
After installation, point your browser to: `https://{{ansible_fqdn}}/{{nginx_reverse_proxy_path}}` eg: https://fqdn/rdp 
Default username and password is: `guacadmin`  
*(Don't forget to change it)*

---
