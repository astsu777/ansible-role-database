Ansible Role: Database
=========

This role installs and secures the latest version of MariaDB server


Requirements
------------

No specific requirements for this role.

Role Variables
--------------

The only variable of this role would be the root's password for MariaDB:

```mysql_root_password: MyPass```

That particular variable should be defined in host_vars and should be encrypted using *ansible-vault*.

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

My name is Gaétan. You can follow me on [Twitter](https://twitter.com/gaetanict)

Website: [ICT Pour Tous](https://www.ictpourtous.com)
