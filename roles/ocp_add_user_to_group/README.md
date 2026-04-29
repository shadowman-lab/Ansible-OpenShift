<!-- This was created with Claude Code -->

ocp_add_user_to_group
=====================

An Ansible role for ocp add user to group.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **ocp_group**: Group name or identifier
  - Default: `admins`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: ocp_add_user_to_group
      vars:
        ocp_group: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
