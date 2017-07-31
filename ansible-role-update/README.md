# Ansible role `update`
======================

Playbook para instalar o Command Line Tools.

## Requirements
---------------

Nenhum (exceto estar usando um Mac OS X).

## Role Variables
-----------------

`force_install`: Instala o Command Line Tools, mesmo que já estejam instalados (Default: `no`).
`osx_update_install`: True
`osx_update_recommended_only`: True
`osx_update_download_only`: False

## Dependencies
---------------

Nenhuma.

## Example Playbook
-------------------

A simple playbook example:

    - hosts: servers
      roles:
         - { role: ansible-role-update }


## License
----------

[MIT][mit-link]

## Author Information
---------------------
