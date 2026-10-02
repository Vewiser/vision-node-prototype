# 06 // Validation and Backup

## Ubuntu baseline

- [ ] Ubuntu Server 26.04.1 LTS boots from NVMe.
- [ ] Six CPU cores and approximately 16 GB RAM appear.
- [ ] The 500 GB NVMe reports healthy.
- [ ] System updates complete without errors.
- [ ] SSH key login works from a trusted device.
- [ ] UFW allows only intended access.
- [ ] The node returns after a controlled reboot.
- [ ] Two Wi-Fi-only reboots succeed.
- [ ] No router port forwards expose the node.
- [ ] The administrator password is unique and privately stored.
- [ ] `systemctl --failed` reports no unexplained failures.

## Container baseline

- [ ] Docker Engine and Compose versions are recorded.
- [ ] The hello-world container runs and removes cleanly.
- [ ] One low-risk service starts, stops, and recreates cleanly.
- [ ] Persistent data location is understood.
- [ ] The Docker socket is not exposed.
- [ ] The host remains responsive under normal container load.

## VM and isolation baseline

- [ ] KVM acceleration is available.
- [ ] One Ubuntu test VM boots with 2 vCPU and 4 GB RAM.
- [ ] The guest uses libvirt's default NAT network.
- [ ] Host remains responsive while the VM runs.
- [ ] VM shutdown, snapshot, and deletion are understood.
- [ ] No vulnerable target exists before isolation testing.
- [ ] The lab cannot reach trusted home devices.

## Backup policy

Prototype 01 has one NVMe, so a second copy must exist on another physical device or trusted system.

| Asset | Backup |
| --- | --- |
| Important files | Separate physical destination |
| Docker configuration | Compose files plus exported configuration |
| Persistent app data | Separate encrypted backup |
| VM definitions/images | Separate storage when worth preserving |
| GitHub docs/IaC | GitHub plus local clone |
| Private recovery data | Encrypted private record |
| Cloud resources | Re-creatable code, not irreplaceable state |

## Restore exercise

1. Back up a disposable test folder.
2. Restore it to a new location.
3. Compare contents.
4. Recreate one low-risk Docker service.
5. Reboot and verify the service returns.
6. Record the result without exposing private details.

## Completion gate

- [ ] Ubuntu baseline passes.
- [ ] Independent backup and restore pass.
- [ ] Docker lifecycle is documented.
- [ ] First VM lifecycle is documented.
- [ ] Cloud budget alert and teardown are tested.
- [ ] Build log is current.

Only then unlock intentionally vulnerable security-lab targets.
