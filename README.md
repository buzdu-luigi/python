Python
===============

Ansible role for installing a particular version of Python from source.

Requirements
------------

None

Role Variables
--------------

The only role vars that the user needs to worry about are:

- `pyfsrc_version`: The version of python to install
- `pyfsrc_make_default`: Whether to make this version of python the
  default version on the system.
- `pyfsrc_force_install`: Install again even if the specified version
  is already found.
- `pyfsrc_ssl_support`: add python support for ssl
- `pyfsrc_install_pip`: install pip and setuptools

Dependencies
------------

None

Example Playbook
----------------

eg:

```
- hosts: test
  connection: local
  roles:
    - apache
  become: true
  become_user: root
  become_method: su
  become_exe: 'sudo su -'
```

The above playbook will install python version 3.4.3.

The role can be used multiple times with different value of
`pyfsrc_version` to install different versions. This can be useful for
setting up an environment for testing a python lib against multiple
versions by using tox for eg.
