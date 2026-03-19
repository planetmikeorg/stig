# STIG Ansible Playbooks

This repository contains Ansible playbooks for DISA STIG controls on RHEL 8 and RHEL 9.

## Folder Layout

- `RHEL-08/` RHEL 8 STIG remediations
- `RHEL-09/` RHEL 9 STIG remediations

## Quick Start

1. Run from the folder that contains the target playbook.
2. Use an inventory appropriate for your environment.
3. Provide required variables and vault files where noted in each playbook.

Example:

```bash
ansible-playbook -i inventory.ini RHEL-09/RHEL-09-213020.yml
```

## Notes

- Some controls are intentionally strict and may affect user or application behavior.
- Review and test each playbook in a non-production environment before broad rollout.
- Read the folder-specific README files for variable requirements and control-specific notes.
