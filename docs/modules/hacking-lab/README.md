# VISION NODE // Isolated Cyber Lab

> A legal, contained environment for understanding attacks and improving defenses.

## Status

**Locked until ZVM network isolation is proven.**

ZimaOS is the Prototype 01 host. The lab may use ZVM only if the installed stable release can create and verify a network that does not route to the home LAN, router, internet, or ZimaOS management interface.

If that boundary cannot be proven, do not run vulnerable targets locally. Continue with safe CTF platforms, a disposable Kali workstation, and defensive cloud experiments instead.

## Scope

Allowed:

- Intentionally vulnerable machines you own
- Disposable applications designed for training
- CTF challenges
- Systems covered by explicit written authorization

Not allowed:

- Third-party systems
- Neighboring or public Wi-Fi
- Production, client, dental, family, or studio systems
- Publicly exposed vulnerable cloud instances

## Resource budget

| System | vCPU | RAM | Disk | Rule |
| --- | ---: | ---: | ---: | --- |
| ZimaOS reserve | — | 6–8 GB | Host-managed | Always preserved |
| Kali workstation | 2 | 4 GB | 60 GB | One substantial VM at a time |
| Vulnerable target | 1–2 | 2 GB | 20–40 GB | Only after isolation proof |

## Unlock sequence

1. Install and validate ZimaOS.
2. Complete an independent backup and restore.
3. Create the safe Ubuntu ZVM guest.
4. Learn ZVM start, stop, console, network, and deletion.
5. Prove an isolated ZVM network with harmless guests.
6. Record the isolation test.
7. Create Kali from an official, checksum-verified image.
8. Add one intentionally vulnerable target.
9. Train using the defensive journal and cleanup checklist.

## Two-mode rule

### Update mode

- Vulnerable target is off.
- Kali receives temporary outbound access only.
- Kali is updated from official repositories.
- Outbound access is detached after shutdown.

### Lab mode

- Kali and target use only the proven isolated network.
- No physical LAN or internet route exists.
- No real data or credentials are present.
- Both guests are shut down when training ends.

## Supporting documents

The earlier KVM/libvirt documents remain as technical reference, but ZVM's current interface and official documentation control this Prototype 01 implementation.

- [Charter](00-charter.md)
- [Isolation concepts](02-isolated-network.md)
- [Kali workstation](03-kali-workstation.md)
- [Targets and defensive learning](04-targets-and-learning-path.md)
