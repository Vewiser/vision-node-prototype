# 06 // Validation and Backup

## Ubuntu Desktop baseline

- [ ] Ubuntu Desktop 26.04.1 LTS boots from NVMe.
- [ ] The desktop is responsive at the intended display resolution.
- [ ] Six CPU cores and approximately 16 GB RAM appear.
- [ ] The 500 GB NVMe reports healthy.
- [ ] System updates complete without errors.
- [ ] SSH key login works from a trusted device.
- [ ] UFW allows only intended access.
- [ ] Two Wi-Fi-only reboots succeed.
- [ ] The node runs continuously for 48 hours.
- [ ] No router port forwards expose the node.
- [ ] The administrator password is unique and privately stored.
- [ ] `systemctl --failed` reports no unexplained failures.

## First-service proof

- [ ] One low-risk Docker service is installed.
- [ ] It starts, stops, and recreates cleanly.
- [ ] It returns after a controlled reboot.
- [ ] Persistent data location is understood.
- [ ] The Docker socket is not exposed.
- [ ] The host remains responsive.

## VM and isolation baseline

- [ ] KVM acceleration is available.
- [ ] One Ubuntu test VM boots with 2 vCPU and 4 GB RAM.
- [ ] The guest uses libvirt's default NAT network.
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

## Proof 001

Document one complete, sanitized walkthrough:

1. Ubuntu Desktop boots and reconnects to Wi-Fi.
2. SSH key login succeeds.
3. One Docker service is reachable.
4. The service survives a reboot.
5. Disposable data is backed up.
6. The data is restored to a new location.
7. No private addresses, credentials, or identifiers are published.

## Completion gate

- [ ] Desktop baseline passes.
- [ ] 48-hour stability test passes.
- [ ] Independent backup and restore pass.
- [ ] Proof 001 is documented.
- [ ] First VM lifecycle is documented.
- [ ] Cloud budget alert and teardown are tested.

Only then unlock intentionally vulnerable security-lab targets or begin the Ubuntu Server migration.
