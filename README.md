ansible-role-unixodbc
=========

An Ansible role that installs and configures UnixODBC. The role can also optionally download and install the MySQL ODBC driver (only for Ubuntu 1804 x64 currently).

Requirements
------------

None

Role Variables
--------------

See defaults/main.yml

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: lukasgibb.unixodbc, unixodbc_driver_dl_enabled: true }

License
-------

MIT

Author Information
------------------

This role was created in 2019 by:
[Lukas Gibb](https://github.com/LukasGibb) - [CloudJourneyman.com](http://www.cloudjourneyman.com/)
