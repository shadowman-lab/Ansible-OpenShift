<!-- This was created with Claude Code -->

ocp_node_cleanup
================

Cleans up old container images and logs on OpenShift nodes without requiring
direct SSH access. Two mechanisms are applied through the OpenShift API:

* A `KubeletConfig` that tunes image and container log garbage collection
  thresholds on the kubelet, so it keeps disk usage under control on an
  ongoing basis.
* A `MachineConfig` that drops a journald retention policy onto nodes in the
  target pool.

Applying a `MachineConfig` triggers the Machine Config Operator to drain and
reboot nodes in the pool one at a time, which can take a while on a large
cluster.

Requirements
------------

- Ansible 2.9 or higher
- `redhat.openshift` collection
- OpenShift credentials with permission to manage `KubeletConfig` and
  `MachineConfig` cluster-scoped resources

Role Variables
---------------

* **machine_config_pool**: Machine config pool to target
  - Default: `worker`

* **kubelet_image_min_gc_age**: Minimum age before an unused image is eligible for garbage collection
  - Default: `2m0s`

* **kubelet_image_gc_high_threshold_percent**: Disk usage percent that triggers image garbage collection
  - Default: `80`

* **kubelet_image_gc_low_threshold_percent**: Disk usage percent garbage collection tries to reach
  - Default: `70`

* **container_log_max_size**: Max size of a container log file before rotation
  - Default: `50Mi`

* **container_log_max_files**: Max number of rotated container log files kept per container
  - Default: `3`

* **journald_system_max_use**: Max disk space the persistent systemd journal may use on a node
  - Default: `500M`

* **journald_max_retention_sec**: Max age of journal entries before they're removed
  - Default: `3day`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: localhost
  roles:
    - role: ocp_node_cleanup
      vars:
        machine_config_pool: worker
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
