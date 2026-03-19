# RHEL-08 STIG Playbooks

This folder contains Ansible playbooks for selected RHEL 8 STIG controls.

## Playbooks

| Playbook | STIG | Description |
|---|---|---|
| `RHEL-08-010149.yml` | [RHEL-08-010149](https://stigaview.com/products/rhel8/v2r6/RHEL-08-010149/) | GRUB2 unique superusers name (BIOS systems) |
| `RHEL-08-010150.yml` | [RHEL-08-010150](https://stigaview.com/products/rhel8/v2r6/RHEL-08-010150/) | GRUB2 password requirement (BIOS systems) |
| `RHEL-08-010190.yml` | [RHEL-08-010190](https://stigaview.com/products/rhel8/v2r6/RHEL-08-010190/) | Sticky bit on world-writable directories |
| `RHEL-08-010770.yml` | [RHEL-08-010770](https://stigaview.com/products/rhel8/v2r6/RHEL-08-010770/) | Local initialization files mode 0740 or less permissive |
| `RHEL-08-020352.yml` | [RHEL-08-020352](https://stigaview.com/products/rhel8/v2r6/RHEL-08-020352/) | Enforce umask 077 in local interactive user initialization files |
| `RHEL-08-040137.yml` | [RHEL-08-040137](https://stigaview.com/products/rhel8/v2r6/RHEL-08-040137/) | fapolicyd deny-all, permit-by-exception policy |

## Shared Variables

- `vars.yml` shared variables used by GRUB2-related controls

Expected vault variable:

- `vault_grub2_password_hash`

## Run Examples

```bash
ansible-playbook -i inventory.ini RHEL-08-010150.yml -e @vault.yml --ask-vault-pass
ansible-playbook -i inventory.ini RHEL-08-010149.yml -e @vault.yml --ask-vault-pass
```

## Notes

- GRUB2 controls are not applicable to UEFI systems in the current playbook logic.
- `RHEL-08-010149.yml` and `RHEL-08-010150.yml` can be run independently when required variables are provided.
