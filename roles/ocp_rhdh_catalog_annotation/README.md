<!-- This was created with Claude Code -->

ocp_rhdh_catalog_annotation
============================

Patches the `aap.platform/is_superuser` annotation directly onto a Red Hat
Developer Hub (RHDH) catalog entity in the `final_entities` table, by
exec'ing `psql` inside the RHDH Postgres pod.

This is a workaround, not a fix: `final_entities` is a cache that the
catalog's stitching process recomputes from the owning entity provider's raw
data. If the entity's owning provider (e.g. a GitHub org sync) doesn't carry
this annotation, the patch will be silently overwritten the next time that
entity is re-stitched - which can happen well before the provider's own
refresh schedule. Re-run this playbook whenever the annotation needs to be
reapplied.

Requirements
------------

- Ansible 2.9 or higher
- `redhat.openshift` collection
- OpenShift user with exec permission on the target pod/namespace

Role Variables
--------------

See `defaults/main.yml`:

- `rhdh_namespace`: namespace containing the RHDH Postgres pod
- `rhdh_postgres_pod`: name of the Postgres pod
- `rhdh_postgres_container`: container name within that pod
- `rhdh_catalog_db`: catalog plugin database name
- `rhdh_catalog_entity_ref`: entity ref to patch (e.g. `user:default/adworjan`)
- `rhdh_catalog_annotation_key`: annotation key to set
- `rhdh_catalog_annotation_value`: annotation value to set

Also requires `openshift_fqdn`, `openshift_user`, `openshift_password` for
cluster login (same as `ocp_namespace`).

Example Playbook
----------------

```yaml
- hosts: localhost
  roles:
    - role: ocp_rhdh_catalog_annotation
      vars:
        rhdh_catalog_entity_ref: "user:default/someuser"
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
