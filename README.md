Postfix.SES
=========

Ansible role to configure Amazon SES within Postfix

Example Playbook
----------------

    - hosts: all
      roles:
         - { role: jketelaar.postfix-ses }

License
-------

MIT

TODO items
------------------
- Check if files already exist and have the right content
    - There is no need to recreate files (or even restart postfix) if there is no change
