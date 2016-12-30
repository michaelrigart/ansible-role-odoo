Ansible Odoo Role
=================

An ansible role for installing and configuring Odoo.
The installation happens from a git repository (source), so not from a package.
You can define your own repository and / or version for this.
Only one Odoo instance per host can be installed with this role.

There are also some dependencies:
  * Postgres
  * Git

You might also want to install Nginx or Apache to proxy the requests to your odoo-server process.

I do not use the Ansible dependency system, so you can freely choose which roles you use to install these dependencies.

Role Variables
--------------

```yaml
odoo_user: a dictionary holding all crucial information about the Odoo user and instance
odoo_server_config: a dictionary holding you odoo-server configuration parameters
odoo_daemon: path to the Odoo-server daemon
odoo_config: path to the Odoo configuration file
odoo_directories: list of directories that need to be created
odoo_log: path to the Odoo log file
odoo_service_state: state of the odoo service
odoo_service_enabled: set to enable / disable odoo service
odoo_wkhtmltopdf_package: url to the wkhtmltopdf binary file
```

View the default vars - defaults/main.yml - for a more detailed example.

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - { role: MichaelRigart.odoo, become: true }
```

License
-------

GPLv3

Author Information
------------------

Michaël Rigart <michael@netronix.be>
