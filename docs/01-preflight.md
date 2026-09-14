# 01 // Preflight and Recovery

> Stop: the Proxmox installer will erase the selected 500 GB NVMe.

Do not continue until every required item below is checked.

## Preserve Windows and personal data

- [ ] Copy every required personal file to separate storage.
- [ ] Confirm the backup opens from another computer.
- [ ] Confirm Windows activation is linked to the intended Microsoft account, if applicable.
- [ ] Record the Windows edition: Windows 11 Pro.
- [ ] Create Windows recovery media if you may restore Windows later.
- [ ] Save required application licenses without placing keys in GitHub.
- [ ] Photograph the current BIOS settings for private reference.
- [ ] Confirm the M720q contains only the drive intended for erasure.

A file existing in only one place is not backed up.

## Required equipment

- [ ] M720q and power adapter
- [ ] USB keyboard
- [ ] Temporary monitor/display
- [ ] 8 GB or larger USB drive
- [ ] Wired Ethernet cable
- [ ] Second computer for downloads and administration
- [ ] Independent backup storage
- [ ] Router administration access

## Network worksheet — keep real values private

| Setting | Documentation example |
| --- | --- |
| Router/gateway | `192.0.2.1` |
| Proxmox address | `192.0.2.10/24` |
| DNS server | `192.0.2.1` |
| Hostname | `vision-node-01.example.internal` |

The `192.0.2.0/24` network is documentation-only. Do not blindly enter these example values. Determine your real gateway and DHCP range, then select a reserved address outside the automatic DHCP pool or create a router reservation.

## Download and verify

1. Download the current x86-64 Proxmox VE ISO from the official Proxmox download page.
2. Download a trusted imaging tool such as Balena Etcher or Rufus from its official source.
3. Verify the ISO SHA-256 checksum against the value published by Proxmox.
4. Write the ISO to the USB drive.
5. Safely eject the USB drive.

### Checksum commands

macOS:

```bash
shasum -a 256 ~/Downloads/proxmox-ve_*.iso
```

Windows PowerShell:

```powershell
Get-FileHash "$HOME\Downloads\proxmox-ve_*.iso" -Algorithm SHA256
```

Linux:

```bash
sha256sum ~/Downloads/proxmox-ve_*.iso
```

Proceed only when the computed and published checksums match exactly.

## Go/no-go gate

- [ ] Backup verified
- [ ] Correct target drive identified
- [ ] ISO checksum verified
- [ ] Real network settings recorded privately
- [ ] Ethernet connected
- [ ] Maintenance window available
- [ ] Rollback media available

**Checkpoint:** Commit a redacted preflight update before erasing the drive.
