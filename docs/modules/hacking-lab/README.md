# VISION NODE // Isolated Ethical-Security Lab

> A legal, contained environment for understanding attacks and improving defenses.

## Status

**Locked until KVM/libvirt network isolation is proven.**

Ubuntu Desktop is the Prototype 01 host. The lab uses KVM/libvirt only after the node passes its 48-hour stability test, backup/restore test, and Proof 001. The visual Virtual Machine Manager can help during the first build, but the isolation rules remain strict.

If the lab network cannot be proven separate from the home LAN, router, internet, and host-management services, do not run vulnerable targets locally. Continue with reputable CTF platforms and defensive exercises instead.

## Scope

Allowed:

- Intentionally vulnerable machines you own
- Disposable applications designed for training
- CTF challenges
- Systems covered by explicit written authorization

Not allowed:

- Third-party systems without permission
- Neighboring or public Wi-Fi
- Production, client, dental, family, or studio systems
- Publicly exposed vulnerable cloud instances
- Denial-of-service, persistence, or destructive testing outside a disposable lab

## Resource budget

| System | vCPU | RAM | Disk | Rule |
| --- | ---: | ---: | ---: | --- |
| Ubuntu Desktop reserve | — | At least 6 GB | Host-managed | Always preserved |
| Kali workstation | 2 | 4 GB | 60 GB | One substantial VM at a time |
| Vulnerable target | 1–2 | 2 GB | 20–40 GB | Only after isolation proof |

## Unlock sequence

1. Install and secure Ubuntu Desktop.
2. Complete the 48-hour stability test.
3. Complete an independent backup and restore.
4. Document Proof 001.
5. Install and validate KVM/libvirt and Virtual Machine Manager.
6. Create a safe Ubuntu test guest.
7. Learn VM start, stop, console, snapshot, and deletion.
8. Build an isolated libvirt network with harmless guests.
9. Prove the network cannot reach trusted home devices.
10. Create Kali from an official checksum-verified image.
11. Add one intentionally vulnerable target.
12. Train, document remediation, restore, and clean up.

## Two-mode rule

### Update mode

- Vulnerable target is off.
- Kali receives temporary outbound access only.
- Kali is updated from official repositories.
- Outbound access is removed after shutdown.

### Lab mode

- Kali and target use only the proven isolated network.
- No physical LAN or internet route exists.
- No real data or credentials are present.
- Both guests are shut down when training ends.

## Supporting documents

- [Charter](00-charter.md)
- [KVM foundation](01-kvm-foundation.md)
- [Isolated network](02-isolated-network.md)
- [Kali workstation](03-kali-workstation.md)
- [Targets and defensive learning](04-targets-and-learning-path.md)
