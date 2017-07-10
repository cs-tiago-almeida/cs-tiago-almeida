role-update_osx
================

An Ansible role to setup Xcode, Command Line Tools and rbenv on OS X

Requirements
------------
[Homebrew](http://brew.sh/) must be installed.
[mas](https://github.com/mas-cli/mas) on macOS, and installs macOS apps from the Mac App Store.

Role Variables
--------------
-   rbenv
-   update


Role Variables
--------------
-   mas_email: "Your appleid appstore user"
-   mas_password: "Your appleid appstore password"
-   mas_installed_app_ids: [] # Deprecated
-   mas_installed_apps:
  - { id: 1127487414, name: "macOS Sierra (10.12.5)" }
  - { id: 497799835, name: "Xcode (8.3.3)" }

mas_upgrade_all_apps: no
mas_signin_dialog: no

The credentials of the Mac App Store account. The applications you have installed must be purchased/registered by this account.

The file with the credentials is in `vars / main.yml` encrypted with ansible-vault.

    mas_signin_dialog: no
If set to _yes_, you must specify the `mas_email` variable mentioned above that will be automatically populated in the dialog box and prompts you to enter your password, followed by the authorization code 2FA if enabled in the account.

-   mas_installed_app_ids: [] # Deprecated
-   mas_installed_apps:
  - { id: 1127487414, name: "macOS Sierra (10.12.5)" }
  - { id: 497799835, name: "Xcode (8.3.3)" }

A list of applications to ensure are installed on your computer. You can get IDs for all your existing installed applications with `but list` and you can search for IDs with` but search [App Name] `. The `name` attribute is not authoritative and is only used to provide better information in the playbook output.


Example Playbook
----------------
---
- name: Install Server
  hosts: company
  gather_facts: no
  become_user: root

  roles:
    - rbenv
    - update

License
-------
MIT

Author Information
------------------
[Tiago de Almeida Francisco] (repo)
