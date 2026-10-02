# Future // Ubuntu Server Upgrade Path

Ubuntu Desktop is the Prototype 01 starting point. Ubuntu Server is the later lean, headless direction after the operator is comfortable with Linux and the node's services can be rebuilt from documentation.

## Why defer Server

Desktop provides a visual safety net for Wi-Fi, display, storage, updates, and recovery. The terminal and core Ubuntu foundations are still real Linux, so the learning is not wasted.

## When Server becomes worthwhile

Move to Ubuntu Server when most of these are true:

- The Desktop node has run reliably for at least 48 hours.
- Two Wi-Fi-only reboots pass.
- SSH key access and UFW are understood.
- Docker services are defined in Compose files.
- Important data has an independent tested backup.
- You can identify and repair failed services from the terminal.
- The desktop interface is no longer needed for daily operation.
- Reinstalling the M720q does not threaten unique data.

## Migration concept

1. Export a package list and record installed versions.
2. Commit sanitized Docker Compose, scripts, and documentation.
3. Back up persistent data to another physical destination.
4. Prove restoration with disposable test data.
5. Download and verify the current Ubuntu Server LTS ISO.
6. Reinstall Ubuntu Server on the M720q.
7. Restore SSH, firewall, Wi-Fi, Docker, monitoring, and backups one layer at a time.
8. Run the full validation checklist again.
9. Unlock KVM and the security lab only after the new baseline passes.

## What stays the same

- Hostname and documented purpose
- GitHub as the source of truth
- Docker Compose services
- Cloud-engineering projects
- KVM/libvirt direction
- Permission-only security lab
- Wi-Fi-first operating requirement
- Backup, recovery, and proof standards

Ubuntu Server is an operational upgrade, not a requirement for beginning the project.
