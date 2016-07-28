ansible-role-zsh [![Build Status](https://travis-ci.org/mlangry/ansible-role-zsh.svg?branch=master)](https://travis-ci.org/mlangry/ansible-role-zsh)
=========

An Ansible role to install and configure zsh

Requirements
------------

None

Role Variables
--------------

````yaml
zsh_user: {{ ansible_user_id }}
zsh_default_shell: yes
zsh_default_shell_for_new_user: yes
# zshrc file path to copy
# zsh_rc_file_source_path:
zsh_rc_file_path: "/home/{{ zsh_user }}/.zshrc"
# global zshrc file path to copy
# zsh_global_rc_file_source_path:
zsh_global_rc_file_path: /etc/zsh/zshrc
````

Dependencies
------------

None

Example Playbook
----------------

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
      zsh_user: user1
      zsh_rc_file_source_path: zshrc1

    - role: ansible-role-zsh
      zsh_user: user2
      zsh_rc_file_source_path: zshrc2
````

License
-------

MIT
