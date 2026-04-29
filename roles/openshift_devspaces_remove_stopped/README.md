<!-- This was created with Claude Code -->

openshift_devspaces_remove_stopped
==================================

An Ansible role for openshift devspaces remove stopped.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **timeinsecondsbeforedelete**: Variable used in: {{ item.metadata.name }}
  - Default: `172800`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: openshift_devspaces_remove_stopped
      vars:
        timeinsecondsbeforedelete: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
