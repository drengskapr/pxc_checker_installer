PXC-checker installer
=========

Installs [pxc-checker](https://github.com/larrabee/pxc-checker).

Requirements
------------

Ubuntu 20.04+
Debian 10+

Might work on older versions. I didn't check.

Role Variables
--------------

`pxc_checker_version` -- required version of `pxc-checker` package.

`pxc_checker_monitor_user` -- user which will monitor node's availability. Has to exist on pxc-cluster.

`pxc_checker_monitor_password` -- `pxc_checker_monitor_user`'s password.

`pxc_checker_user` -- system user which runs `pxc-checker@cluster` service.

`pxc_checker_group` -- system user's group 

Dependencies
------------

Running PXC-cluster

Example Playbook
----------------

```
- name: Setting up PXC-checker
  hosts: all
  remote_user: root
  roles:
    - pxc-checker_installer
  vars:
    pxc_checker_version: 0.12.02
    pxc_checker_monitor_user: user
    pxc_checker_monitor_password: user
    pxc_checker_user: another_user
    pxc_checker_group: another_user
```

License
-------

BSD

