# RHEL-09 STIG Playbooks

This folder contains Ansible playbooks for selected RHEL 9 STIG controls.

## Playbooks

| Playbook | STIG | Description |
|---|---|---|
| `RHEL-09-213020.yml` | [RHEL-09-213020](https://stigaview.com/products/rhel9/v2r7/RHEL-09-213020/) | Disable loading a new kernel for later execution (kexec) |
| `RHEL-09-231200.yml` | [RHEL-09-231200](https://stigaview.com/products/rhel9/v2r7/RHEL-09-231200/) | Enforce `nodev` on non-root local partitions (except vfat) |
| `RHEL-09-232240.yml` | [RHEL-09-232240](https://stigaview.com/products/rhel9/v2r7/RHEL-09-232240/) | World-writable directories must be owned by root or a system account |
| `RHEL-09-411055.yml` | [RHEL-09-411055](https://stigaview.com/products/rhel9/v2r7/RHEL-09-411055/) | Restrict PATH in local interactive user initialization files |
| `RHEL-09-411095.yml` | [RHEL-09-411095](https://stigaview.com/products/rhel9/v2r7/RHEL-09-411095/) | Detect/remove unauthorized local interactive accounts |
| `RHEL-09-433016.yml` | [RHEL-09-433016](https://stigaview.com/products/rhel9/v2r7/RHEL-09-433016/) | fapolicyd deny-all, permit-by-exception policy |
| `RHEL-09-611085.yml` | [RHEL-09-611085](https://stigaview.com/products/rhel9/v2r7/RHEL-09-611085/) | Require password for sudo privilege escalation |
| `RHEL-09-651010.yml` | [RHEL-09-651010](https://stigaview.com/products/rhel9/v2r7/RHEL-09-651010/) | Ensure AIDE package is installed and initialized |

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
