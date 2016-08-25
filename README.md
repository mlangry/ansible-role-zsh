ansible-role-zsh [![Build Status](https://travis-ci.org/mlangry/ansible-role-zsh.svg?branch=master)](https://travis-ci.org/mlangry/ansible-role-zsh)
=========

An Ansible role to install and configure zsh

Requirements
------------

None

Role Variables
--------------

````yaml
zsh_users:
  - "{{ ansible_user_id }}"
# -  { user: username, zsh_rc_file_path: zsh_rc_file_path, default_shell: yes }
zsh_default_shell_for_new_user: yes
# global zshrc file path to copy
# zsh_global_rc_file_source_path:
zsh_global_rc_file_path: /etc/zsh/zshrc
````

Dependencies
------------

None

Example Playbook
----------------
By default zsh is configured for connected user.

````yaml
- hosts: servers
  roles:
     - { role: mlangry.zsh }
````
If you want to configure zsh for multiple users:

````yaml
- hosts: servers
  roles:
    - role: ansible-role-zsh
      zsh_users:
        - { user: user1, zsh_rc_file_path: zshrc1, default_shell: yes }
        - { user: user2 }
        - { user: user3, default_shell: no }
        - user4
````

By default zsh is set as the default shell for user.

License
-------

MIT
