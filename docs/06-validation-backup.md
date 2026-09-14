# 06 // Validation and Backup

## ZimaOS baseline

- [ ] Dashboard opens from a trusted LAN device.
- [ ] Six CPU cores and approximately 16 GB RAM appear.
- [ ] The 500 GB NVMe appears healthy.
- [ ] Wired networking and DNS work.
- [ ] System updates complete.
- [ ] The node returns after a controlled reboot.
- [ ] No router port forwards expose the dashboard.
- [ ] The administrator password is unique and privately stored.

## App and VM baseline

- [ ] One low-risk app installs, starts, stops, and removes cleanly.
- [ ] Persistent app data location is understood.
- [ ] ZVM detects Intel virtualization.
- [ ] One test VM boots with 2 vCPU and 4 GB RAM.
- [ ] Host remains responsive while the VM runs.
- [ ] VM shutdown and deletion are understood.
- [ ] A cyber target has not been created before isolation testing.

## Backup policy

Prototype 01 has one NVMe, so a second copy must exist on another physical device or system.

| Asset | Backup |
| --- | --- |
| Important files | Separate physical destination |
| App configuration | Export or documented recreation steps |
| VM images | Separate storage when worth preserving |
| GitHub docs/IaC | GitHub plus local clone |
| Private recovery data | Encrypted private record |
| Cloud resources | Re-creatable code, not irreplaceable server state |

## Restore exercise

1. Back up a disposable test folder.
2. Restore it to a new location.
3. Compare contents.
4. Recreate one low-risk app from documented settings.
5. Record the result without exposing private details.

## Completion gate

- [ ] ZimaOS baseline passes.
- [ ] Independent backup and restore pass.
- [ ] First ZVM lifecycle is documented.
- [ ] Cloud budget alert and teardown are tested.
- [ ] Build log is current.

Only then unlock vulnerable cyber-lab targets.
