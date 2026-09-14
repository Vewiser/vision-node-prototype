# 01 // Preflight and Recovery

> Stop: installing Ubuntu on the selected 500 GB NVMe will erase Windows and its files.

## Preserve Windows and personal data

- [ ] Copy every required personal file to separate storage.
- [ ] Open several backed-up files from another computer.
- [ ] Confirm Windows activation is linked to your Microsoft account, if applicable.
- [ ] Create Windows recovery media if you may restore Windows later.
- [ ] Save required license information privately.
- [ ] Confirm the M720q contains only the drive intended for erasure.

A file existing in only one place is not backed up.

## Required equipment

- [ ] M720q and power adapter
- [ ] Keyboard and temporary monitor
- [ ] 8 GB or larger USB drive
- [ ] Wired Ethernet cable
- [ ] Second computer for downloading Ubuntu
- [ ] Independent backup storage
- [ ] Router administration access

## Simple network plan

Use DHCP during installation. After Ubuntu is working, create a DHCP reservation for the node in the router.

| Setting | Public documentation example |
| --- | --- |
| Hostname | `vision-node-01` |
| Example server address | `192.0.2.10` |
| Connection | Wired Ethernet |
| Remote administration | SSH from trusted LAN only |

`192.0.2.0/24` is reserved for documentation. Never copy it as your real configuration.

## Download and verify Ubuntu

1. Download the current Ubuntu Server 26.04.1 LTS x86-64 ISO from Ubuntu.
2. Download Balena Etcher or Rufus from its official source.
3. Obtain Ubuntu's published SHA-256 checksum.
4. Calculate the downloaded ISO checksum.
5. Continue only if both values match.
6. Write the ISO to the USB drive and safely eject it.

macOS:

```bash
shasum -a 256 ~/Downloads/ubuntu-*-live-server-amd64.iso
```

Windows PowerShell:

```powershell
Get-FileHash "$HOME\Downloads\ubuntu-*-live-server-amd64.iso" -Algorithm SHA256
```

Linux:

```bash
sha256sum ~/Downloads/ubuntu-*-live-server-amd64.iso
```

## Go/no-go gate

- [ ] Backup verified
- [ ] Correct NVMe identified
- [ ] Ubuntu ISO checksum verified
- [ ] Ethernet connected
- [ ] Router access available
- [ ] Windows recovery decision completed
- [ ] Enough uninterrupted time available

**Checkpoint:** Do not erase the disk until every item above is complete.
