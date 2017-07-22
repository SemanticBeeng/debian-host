debian-host
===========

Initialize and configure a debian system

Requirements
------------

This role requires Ansible 2.3 or higher.

Role Variables
--------------

None

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

Nicolas Blondy <nicolas@famille-blondy.fr>


