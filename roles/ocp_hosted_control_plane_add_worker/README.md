<!-- This was created with Claude Code -->

ocp_hosted_control_plane_add_worker
===================================

An Ansible role for ocp hosted control plane add worker.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **version**: Version number or identifier
  - Default: `4.13.27`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: ocp_hosted_control_plane_add_worker
      vars:
        version: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
