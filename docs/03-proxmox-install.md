# 03 // Install Proxmox VE 9.2

This procedure targets the Lenovo M720q with one 500 GB NVMe. It destroys the selected disk.

## Installer decisions

1. Boot the verified Proxmox USB in UEFI mode.
2. Select **Install Proxmox VE (Graphical)**.
3. Read and accept the license terms.
4. Select the 500 GB NVMe only after matching its capacity and device identity.
5. Open **Options** before continuing.

## Storage recommendation

For this single-drive learning node, use the installer's default LVM-thin layout. It is straightforward, appropriate for one disk, and leaves Proxmox managing guest storage efficiently.

Suggested installation targets:

| Setting | Target |
| --- | --- |
| Filesystem | ext4 with LVM-thin/default |
| Host root | Approximately 64–96 GB |
| VM storage | Remaining LVM-thin capacity |
| Swap | Installer default is acceptable |
| ZFS | Do not use for Prototype 01's single 500 GB drive and 16 GB RAM |

Exact advanced-storage fields can change between installer releases. If the installer does not expose a field described here, retain its documented default and record the difference in the build log.

## Regional settings

Select the correct country, time zone, and keyboard layout. Accurate time is essential for TLS certificates, authentication, and logs.

## Administrator identity

- Use a unique, strong root password stored in a password manager.
- Use a monitored administrative email address.
- Never photograph, publish, or commit either value.

## Network management

Select the physical wired Ethernet interface—not Wi-Fi.

| Field | Safe pattern |
| --- | --- |
| Hostname | `vision-node-01.your-private-domain` |
| Address | Reserved/static address with CIDR |
| Gateway | Router address |
| DNS | Router or trusted internal DNS |

Proxmox expects a fully qualified hostname. Use your real private domain if you operate one; otherwise use a private internal naming convention consistently. Do not use a public domain you do not control.

## Final confirmation

Before clicking **Install**, verify:

- [ ] Target is the 500 GB NVMe.
- [ ] No required Windows data remains solely on that drive.
- [ ] Wired interface is selected.
- [ ] Address, prefix, gateway, and DNS are internally consistent.
- [ ] Hostname is spelled correctly.
- [ ] Root password is stored securely.

Install, reboot, remove the USB when prompted, and allow the M720q to boot from NVMe.

## First connection

From another trusted device on the same LAN, open:

```text
https://YOUR-PROXMOX-IP:8006
```

A certificate warning is expected initially because Proxmox uses a locally generated certificate. Confirm the address is your node before proceeding. Sign in to the Linux PAM realm as `root`.

Do not forward port 8006 through the router.

**Success condition:** the Proxmox web interface loads over wired LAN and shows the node with expected CPU, RAM, and storage.
