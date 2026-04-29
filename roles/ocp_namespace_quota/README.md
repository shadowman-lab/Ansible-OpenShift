<!-- This was created with Claude Code -->

ocp_namespace_quota
===================

An Ansible role for ocp namespace quota.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **requests_cpu**: CPU configuration or limit
  - Default: `2`

* **limits_cpu**: Limit or threshold value
  - Default: `3`

* **requests_memory**: Memory configuration or limit
  - Default: `5Gi`

* **limits_memory**: Limit or threshold value
  - Default: `10Gi`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: ocp_namespace_quota
      vars:
        requests_cpu: <value>
        limits_cpu: <value>
        requests_memory: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
