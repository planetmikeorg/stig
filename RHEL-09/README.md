# RHEL-09 STIG Playbooks

This folder contains Ansible playbooks for selected RHEL 9 STIG controls.

## Playbooks

- `RHEL-09-213020.yml` Disable loading a new kernel for later execution (kexec)
- `RHEL-09-231200.yml` Enforce `nodev` on non-root local partitions (except vfat)
- `RHEL-09-411055.yml` Restrict PATH in local interactive user initialization files
- `RHEL-09-411095.yml` Detect/remove unauthorized local interactive accounts
- `RHEL-09-433016.yml` fapolicyd deny-all, permit-by-exception policy
- `RHEL-09-611085.yml` Require password for sudo privilege escalation
- `RHEL-09-651010.yml` Ensure AIDE package is installed and initialized

## Supporting Files

- `files/RHEL-09-213020/99-kernel_kexec_load_disabled.conf` source file copied by `RHEL-09-213020.yml`
- `files/RHEL-09-433016/fapolicyd.conf` source file copied by `RHEL-09-433016.yml`
- `files/RHEL-09-433016/99-deny-all.rules` source file copied by `RHEL-09-433016.yml`

## Run Examples

```bash
ansible-playbook -i inventory.ini RHEL-09-611085.yml
ansible-playbook -i inventory.ini RHEL-09-433016.yml
```

## Notes

- `RHEL-09-411095.yml` requires `authorized_interactive_users` and defaults to report-only behavior unless `remove_unauthorized_accounts=true` is set.
- `RHEL-09-231200.yml` uses `ansible.posix.mount`; ensure the `ansible.posix` collection is available.
