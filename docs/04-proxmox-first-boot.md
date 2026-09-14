# 04 // Proxmox First Boot

Complete these actions before creating workloads.

## 1. Verify the host

In the web interface confirm:

- [ ] Node name is correct.
- [ ] Six CPU cores are visible.
- [ ] Approximately 16 GB RAM is visible.
- [ ] `local` storage exists for ISO/templates/backups.
- [ ] `local-lvm` exists for guest disks.
- [ ] Network bridge `vmbr0` uses the wired NIC.
- [ ] Gateway and DNS work.
- [ ] Time is correct.

## 2. Update safely

Use the Proxmox web interface to review configured repositories. A paid enterprise repository requires a subscription. For a personal, non-production lab, Proxmox documents the no-subscription repository; it is less heavily tested than enterprise packages.

Do not paste unreviewed “post-install scripts” from forums into the host. Configure repositories using current official Proxmox documentation, refresh package indexes, review pending changes, then update.

From the node shell:

```bash
apt update
apt full-upgrade
pveversion -v
```

Reboot if a new kernel was installed:

```bash
systemctl reboot
```

## 3. Create a named administrator

Avoid routine browser use of the root account.

1. Create a Proxmox user in the `pve` realm.
2. Assign only the permissions needed for administration.
3. Enable two-factor authentication.
4. Test the new account in a private browser window.
5. Retain root credentials securely for recovery.

Do not disable root recovery access until the named account is proven.

## 4. Basic protection

- Keep the management interface reachable only from the trusted LAN.
- Do not create router port forwarding for 8006 or 22.
- Use a VPN such as Tailscale or WireGuard later for remote access.
- Enable the Proxmox firewall only after creating and testing rules that preserve management access.
- Keep one local keyboard/display recovery path available.
- Configure email or another alerting channel later.

## 5. Upload Ubuntu ISO

1. Download Ubuntu Server 26.04.1 LTS from Ubuntu.
2. Verify its published checksum.
3. In Proxmox, select `local` → **ISO Images** → **Upload**.
4. Confirm the ISO appears and has a plausible file size.

## 6. Record baseline

Record redacted output from:

```bash
pveversion -v
lscpu
free -h
lsblk
ip -br link
```

Remove IP addresses, MAC addresses, UUIDs, serial numbers, host keys, and tokens before publishing.

**Checkpoint:** the host is current, reachable, recoverable, and contains no production workloads.
