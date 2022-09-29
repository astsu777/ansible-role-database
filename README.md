Ansible Role: Database
=========

This role installs and secures the latest version of MariaDB server


Requirements
------------

No specific requirements for this role.

Role Variables
--------------

Three variables can be configured for this role, although only one is mandatory by default.

The mandatory one is to define the root account's password to manage MariaDB:

```
mysql_root_password: MyPass
```

That particular variable should be defined in host_vars and should be encrypted using *ansible-vault*.

--

However, if the server needs to accept connections from other machines, it is necessary to define the following variables:

```
db_remote_connections: deny (Define the value as *allow* if you wish to allow remote connections)
db_server_bind_address: 1.1.1.1 (This should be the IP address of the server where MariaDB will listen on)
```

These two variables, if you want to define them, can be defined in host_vars for example.


**Note**: if the database server is running on the same server as, for example, your Web server, these variables are not required.


Dependencies
------------

No dependencies from other roles required.

Example Playbook
----------------

Here is a simple example playbook to use this role:

```
hosts: all
user: root
roles:
  - { role: database, tags: [ 'database' ] }
```

TO-DO
-----

For the moment, this Ansible role only handles MariaDB server. The purpose of this role would be to also integrate PostgreSQL and other database servers.

In addition to this, this role will work only on Debian family OS (Debian, Ubuntu, etc...), but needs to be improvied to run on Red Hat family.


License
-------

MIT / BSD

Author Information
------------------

My name is Gaétan. You can follow me on [Twitter](https://twitter.com/astsu777)

Website: [ICT Pour Tous](https://www.ictpourtous.com)
