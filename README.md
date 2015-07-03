ubuntu-unattended
=========

Enable unattended upgrades on Ubuntu machines

Role Variables
--------------

```yaml
---
mail_target:    "mail@example.com"  # The email address to send reports to
reboot_time:    "04:00"             # When to reboot the server after updates
do_reboot:      "true"              # Execute an automated reboot?
do_autoremove:  "false"             # Execute 'apt-get autoremove'?
```

You should ensure `do_reboot` and `do_autoremove` are strings as they are written into the apt configuration and that file expects `true` instead of `True`, which will get written if you pass a bool here.

Example Playbook
----------------

```yaml
---
- hosts: servers
  roles:
    - role: ubuntu-unattended
      mail_target: mymail@provider.com
      reboot_time: 04:00
      do_reboot: "true"
      do_autoremove: "false"
```

License
-------

Apache 2.0
