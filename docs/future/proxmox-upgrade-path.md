# Future // Proxmox Upgrade Path

Proxmox remains a strong direction, but it is deliberately deferred.

## Why defer it

Bare-metal Ubuntu lets Prototype 01 teach the operating-system foundation with fewer layers. When a command, service, disk, or network connection fails, there is only one Linux environment to inspect.

## When Proxmox becomes worthwhile

Move to Proxmox when at least three of these are true:

- The Ubuntu node is stable and backed up.
- You can administer Linux comfortably through SSH.
- You need multiple isolated operating systems.
- You want disposable test environments and snapshots.
- You are ready to separate trusted services from a security lab.
- RAM is upgraded from 16 GB to 32 GB or more.
- A second physical backup destination is available.
- Reinstalling the M720q no longer threatens unique data.

## Future migration concept

1. Back up application data and sanitized configuration.
2. Prove restoration on another system or temporary environment.
3. Install Proxmox on the M720q.
4. Create an Ubuntu Server guest.
5. Restore services into the guest.
6. Add isolated lab guests only after the core service guest is stable.

The earlier Proxmox direction remains visible in Git history. Prototype 02 can restore and expand it without pretending Prototype 01 needed that complexity.
