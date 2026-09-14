# 06 // Validation and Backup

The node is ready only when it can be checked, restarted, and recovered.

## System validation

Run:

```bash
hostnamectl
lscpu
free -h
lsblk
df -h
systemctl --failed
sudo apt update
```

Success means:

- [ ] Hostname is `vision-node-01`.
- [ ] Six CPU cores and approximately 16 GB RAM are visible.
- [ ] The NVMe and filesystem appear healthy.
- [ ] No unexplained failed services exist.
- [ ] Package repositories are reachable.
- [ ] Wired networking and DNS work.
- [ ] SSH key login works from the trusted workstation.
- [ ] The server returns after a controlled reboot.
- [ ] No router port forwarding exposes SSH or dashboards.

## Backup strategy

Prototype 01 has one internal NVMe. A second copy must live on another physical device.

| Asset | Method | Minimum frequency |
| --- | --- | --- |
| Important project data | `rsync`, restic, or borg to separate storage | Weekly |
| System configuration notes | Sanitized GitHub documentation | After material changes |
| Private recovery details | Encrypted private record | After material changes |
| Container definitions later | Sanitized Compose files | After changes |
| Databases later | Application-aware export plus backup | Scheduled per importance |

GitHub is a documentation and configuration-history layer, not a full server backup.

## First recovery exercise

1. Back up one non-sensitive test directory to separate storage.
2. Delete only a disposable test copy.
3. Restore it to a new directory.
4. Compare the restored contents.
5. Record the successful test in the build log.

Do not practice deletion with unique or valuable data.

## Completion gate

- [ ] Ubuntu baseline passes.
- [ ] SSH access is proven.
- [ ] Firewall state is verified.
- [ ] Independent backup succeeds.
- [ ] Test restore succeeds.
- [ ] Build log is updated.

Only then proceed to Docker applications, remote VPN access, network services, or security tooling.
