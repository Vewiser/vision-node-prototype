# 06 // Validation and Backup

The node is not operationally complete until it can be checked and recovered.

## Host validation

- [ ] Proxmox loads at the expected private address.
- [ ] No router port forwards expose Proxmox or SSH.
- [ ] CPU reports six cores.
- [ ] Memory reports approximately 16 GB.
- [ ] NVMe and LVM-thin storage are healthy.
- [ ] Package updates complete without errors.
- [ ] Correct time and DNS resolution are confirmed.
- [ ] Named administrator and 2FA are tested.
- [ ] Local root recovery remains available.
- [ ] Node returns after a controlled reboot.

## Vision Core validation

Run inside Ubuntu:

```bash
hostnamectl
free -h
df -h
systemctl --failed
sudo apt update
```

Success means:

- [ ] Hostname is `vision-core-01`.
- [ ] Expected CPU, RAM, and disk are visible.
- [ ] No failed systemd units require investigation.
- [ ] Package repositories are reachable.
- [ ] SSH key login works from the trusted workstation.
- [ ] QEMU guest agent reports to Proxmox.
- [ ] VM stops and starts cleanly.

## Backup strategy

Prototype 01 has one internal NVMe. Therefore:

- Snapshots protect against some configuration mistakes.
- Snapshots do not protect against NVMe failure, theft, fire, or node loss.
- A real backup must be stored on another physical device or system.
- Critical repository documentation also lives on GitHub, but GitHub is not a VM backup.

Minimum initial policy:

| Asset | Method | Frequency | Destination |
| --- | --- | --- | --- |
| Vision Core VM | Proxmox backup | Weekly and before major changes | Separate storage |
| Proxmox configuration notes | Sanitized documentation | After material changes | GitHub |
| Private recovery data | Encrypted record | After material changes | Password manager/private backup |
| VM baseline | Snapshot | Before experiments | Same node; temporary |

## Restore test

A backup is unproven until restored.

1. Create an independent backup of Vision Core.
2. Record duration and resulting file size privately.
3. Restore it using a temporary VM ID.
4. Boot the restored VM on an isolated/no-network setting first.
5. Confirm filesystem and services.
6. Delete the temporary restored guest only after validation.
7. Record the successful test without publishing private paths or addresses.

## Completion gate

Phase 1 is complete only when:

- [ ] Host baseline passes.
- [ ] Guest baseline passes.
- [ ] Clean snapshot exists.
- [ ] Independent backup exists.
- [ ] Restore test succeeds.
- [ ] Build log is updated.

Only then proceed to service containers, remote access, automation, VLANs, or an isolated security lab.
