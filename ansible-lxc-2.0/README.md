ansible-lxc
===========

Ansible Connection Plugin to deploy to local lxc containers (https://linuxcontainers.org/)

INSTALL
=======

* Install python2 version of lxc bindings:

   - https://github.com/lxc/python2-lxc

* Clone the plugin in your ansible directory

```
$ mkdir -p /etc/ansible/connection_plugins/
$ git clone git@github.com:Mic92/ansible-lxc.git /etc/ansible/connection_plugins/lxc
```

If your ansible code is already managed by git, you might want to add a submodule instead:

```
$ mkdir -p /etc/ansible/connection_plugins/
$ git submodule add git@github.com:Mic92/ansible-lxc.git /etc/ansible/connection_plugins/lxc
```

* Then add lxc directory to plugin search path in `ansible.cfg`:

```
connection_plugins = /usr/share/ansible_plugins/connection_plugins:/etc/ansible/connection_plugins/lxc
```

USAGE
=====

In your hosts file on the server running lxc use the lxc container name (`examplecontainer` in this case) as hostname and set `ansible_connection` to lxc:

    examplecontainer ansible_connection=lxc
