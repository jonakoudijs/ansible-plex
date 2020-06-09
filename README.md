[![GitHub Workflow Status](https://img.shields.io/github/workflow/status/jonakoudijs/ansible-plex/Galaxy%20Publish?logo=github)](https://github.com/jonakoudijs/ansible-plex/actions)
[![Ansible Galaxy](https://img.shields.io/badge/galaxy-jonakoudijs.plex-blueviolet.svg)](https://galaxy.ansible.com/jonakoudijs/ansible_plex)
[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

Plex Ansible Role
=================

Install Plex on Linux

Requirements
------------

This role needs to be executed as root with `become: true`.

Role Variables
--------------

The following variables are set in `defaults/main.yml` and can be overwritten:
```
plex_repo  # (bool) Use official Plex package repository
```

Dependencies
------------

This role does not have any dependencies.

Example Playbook
----------------

Installing Plex:
```
- hosts: servers
  roles:
     - plex
```

License
-------

[MIT license](LICENSE)

Author Information
------------------

Originally created by [Jona Koudijs](https://www.jona.io).
