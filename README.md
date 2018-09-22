debian-host
===========

Initialize and configure a Debian system

Requirements
------------

This role requires Ansible 2.3 or higher.

Role Variables
--------------

    # Global variables
    # Default users list
    default_users:
        - # root user
            home: /root
            name: root
            gecos:
            shell: zsh
            editor: vim
            vcs: git
            sudo: false
            password: encrypted password by mkpasswd
            ohmyzsh: false
            vundle: false
            authorized_keys:
                - first ssh key
                - second ssh key

    # Defaults packages
    default_packages:
        - openssh-server
        - git
        - locales
        - vim-nox
        - git
        - zsh

    # Variables specific to host
    # Specific user list
    users:
        - # niko user
            home: /home/niko
            name: niko
            gecos: Niko
            shell: zsh
            editor: vim
            vcs: git
            sudo: true
            password: encrypted password by mkpasswd
            ohmyzsh: true
            vundle: true
            authorized_keys:
                - first ssh key
                - second ssh key

    # Defaults packages
    packages:
        - inetutils-ping

Dependencies
------------

This role depends on roles

* toolbox

Example Playbook
----------------

    # On main playbook
    - hosts: pve01
      become: True
      roles:
        - { role: debian-host }

    # Inside another role
    - include_role:
        name: debian-host

License
-------

BSD

Author Information
------------------

Niko <niko@vulpecula.fr>
