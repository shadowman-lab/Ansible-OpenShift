<!-- This was created with Claude Code -->

# OpenShift Automation

[![Contribute](https://img.shields.io/badge/OpenShift-Dev%20Spaces-525C86?logo=redhatopenshift&labelColor=EE0000)](https://devspaces.apps.ocp.shadowman.dev/#https://github.com/shadowman-lab/Ansible-OpenShift)


This directory contains Ansible automation for openshift management and operations.

## Overview

The OpenShift automation provides playbooks and roles for managing and configuring
openshift infrastructure and services.

## Roles

| Role | Description |
| ---- | ----------- |
| [ocp_add_user_to_group](roles/ocp_add_user_to_group/README.md) | Role for ocp add user to group |
| [ocp_build_config](roles/ocp_build_config/README.md) | Role for ocp build config |
| [ocp_deploy](roles/ocp_deploy/README.md) | Role for ocp deploy |
| [ocp_devspaces_git_config](roles/ocp_devspaces_git_config/README.md) | Role for ocp devspaces git config |
| [ocp_hosted_control_plane](roles/ocp_hosted_control_plane/README.md) | Role for ocp hosted control plane |
| [ocp_hosted_control_plane_add_worker](roles/ocp_hosted_control_plane_add_worker/README.md) | Role for ocp hosted control plane add worker |
| [ocp_hosted_control_plane_api_ip](roles/ocp_hosted_control_plane_api_ip/README.md) | Role for ocp hosted control plane api ip |
| [ocp_hosted_control_plane_archive_ocm](roles/ocp_hosted_control_plane_archive_ocm/README.md) | Role for ocp hosted control plane archive ocm |
| [ocp_hosted_control_plane_import](roles/ocp_hosted_control_plane_import/README.md) | Role for ocp hosted control plane import |
| [ocp_hosted_control_plane_remove_worker](roles/ocp_hosted_control_plane_remove_worker/README.md) | Role for ocp hosted control plane remove worker |
| [ocp_hosted_control_plane_subscribe_ocm](roles/ocp_hosted_control_plane_subscribe_ocm/README.md) | Role for ocp hosted control plane subscribe ocm |
| [ocp_namespace](roles/ocp_namespace/README.md) | Role for ocp namespace |
| [ocp_namespace_quota](roles/ocp_namespace_quota/README.md) | Role for ocp namespace quota |
| [ocp_project](roles/ocp_project/README.md) | Role for ocp project |
| [ocp_remove](roles/ocp_remove/README.md) | Role for ocp remove |
| [openshift_devspaces_remove_stopped](roles/openshift_devspaces_remove_stopped/README.md) | Role for openshift devspaces remove stopped |
| [remove_ocp_hosted_control_plane](roles/remove_ocp_hosted_control_plane/README.md) | Role for remove ocp hosted control plane |

## Playbooks

| Playbook | Description | Target Hosts |
| -------- | ----------- | ------------ |
| opa.yml | Playbook for opa | See playbook |
| opa_github.yml | Playbook for opa github | See playbook |
| openshift_build_config_web_app.yml | Playbook for openshift build config web app | localhost |
| openshift_devspaces_gitconfig.yml | Playbook for openshift devspaces gitconfig | localhost |
| openshift_hosted_controlplane.yml | Playbook for openshift hosted controlplane | localhost |
| openshift_hosted_controlplane_api_ip.yml | Playbook for openshift hosted controlplane api ip | localhost |
| openshift_hosted_controlplane_archive_ocm.yml | Playbook for openshift hosted controlplane archive ocm | localhost |
| openshift_hosted_controlplane_import.yml | Playbook for openshift hosted controlplane import | localhost |
| openshift_hosted_controlplane_subscribe_ocm.yml | Playbook for openshift hosted controlplane subscribe ocm | localhost |
| openshift_hosted_controlplane_worker.yml | Playbook for openshift hosted controlplane worker | localhost |
| openshift_namespace_maintain.yml | Playbook for openshift namespace maintain | localhost |
| openshift_namespace_quota.yml | Playbook for openshift namespace quota | localhost |
| openshift_project_maintain.yml | Playbook for openshift project maintain | localhost |
| openshift_remove_hosted_controlplane.yml | Playbook for openshift remove hosted controlplane | localhost |
| openshift_remove_hosted_controlplane_worker.yml | Playbook for openshift remove hosted controlplane worker | localhost |
| openshift_remove_stopped_devspaces.yml | Playbook for openshift remove stopped devspaces | localhost |
| openshift_update_group.yml | Playbook for openshift update group | localhost |
| openshift_web_app.yml | Playbook for openshift web app | localhost |
| openshift_web_app_remove.yml | Playbook for openshift web app remove | localhost |

## Usage

### Running with ansible-navigator

```bash
# Run a playbook
ansible-navigator run openshift_build_config_web_app.yml

# Run in stdout mode
ansible-navigator run openshift_build_config_web_app.yml -m stdout
```

### Using roles

```yaml
- hosts: target_hosts
  roles:
    - ocp_build_config
```

## Requirements

- Ansible 2.9 or higher (via ansible-navigator)
- Required collections (see `collections/requirements.yml` if present)
- Appropriate access credentials configured via environment variables

## Directory Structure

```
Ansible-OpenShift/
├── roles/              # Ansible roles
├── *.yml               # Playbooks
├── collections/        # Collection dependencies (if present)
└── ansible-navigator.yml  # Navigator configuration
```
