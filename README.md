ansible-role-unixodbc
=========

An Ansible role that installs and configures UnixODBC including DSN entries.

The role can also optionally download and install the MySQL ODBC 8.0 driver (only for Ubuntu 1804 x64 currently).

The install basically follows the process outlined in the MySQL documentation:

[Installing Connector/ODBC from a Binary Tarball Distribution](https://dev.mysql.com/doc/connector-odbc/en/connector-odbc-installation-binary-unix-tarball.html)

This install process is very fiddly so there is probably lots of room for improvement in this role. For example, there are some things that I have just hard coded for now due to laziness (eg filenames from within the tar file etc). Having an apt-get package would be much easier but from the research I've done, it appears that no-one maintains the Ubuntu package for the MySQL ODBC driver any longer. I can't really work out why.

In the future I will try to come back and add additional drivers (ie postgresql etc) so that you can just set variables to install the ones you want/need (hopefully with a simple package).

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

    - hosts: servers
      roles:
         - { role: lukasgibb.unixodbc, unixodbc_mysql_dl_enabled: true }

Add your list of DSNs in the host or group variables like this:

    unixodbc_dsns:
      - name: asterisk-connector
        description: MySQL connection to 'asterisk' database
        driver: MySQL ODBC 8.0 Driver
        database: asterisk
        server: 127.0.0.1
        port: 3306
        socket: /var/run/mysqld/mysql.sock

License
-------

MIT

Author Information
------------------

This role was created in 2019 by:
[Lukas Gibb](https://github.com/LukasGibb) - [CloudJourneyman.com](http://www.cloudjourneyman.com/)
