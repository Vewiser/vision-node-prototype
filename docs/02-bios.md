# 02 // M720q BIOS Configuration

Firmware labels can vary by BIOS revision. Record the original value before changing a setting.

## Enter BIOS

1. Shut down the M720q.
2. Connect keyboard, display, Ethernet, and Proxmox USB.
3. Power on and repeatedly press `F1` to enter Setup.
4. If needed, use `F12` for the temporary boot menu.

## Required settings

| Setting | Target | Reason |
| --- | --- | --- |
| Boot mode | UEFI | Modern boot path |
| Intel Virtualization Technology | Enabled | Required for KVM virtual machines |
| VT-d | Enabled | Enables IOMMU/device assignment experiments |
| Secure Boot | Disabled for initial install | Avoids avoidable first-install friction |
| USB boot | Enabled | Boots installer |
| Wake on LAN | Enabled | Remote power-on capability |
| After power loss | Power On or Last State | Recovers after an outage |
| Date/time | Correct UTC/local basis | Prevents certificate and log errors |

Do not enable Intel AMT remote management unless you understand and securely configure it. Unconfigured management interfaces expand the attack surface.

## Boot installer

1. Save settings and exit.
2. Press `F12` during restart.
3. Select the UEFI entry for the Proxmox USB.
4. Confirm that the graphical Proxmox installer appears.

## Validation

- [ ] BIOS detects 16 GB RAM.
- [ ] BIOS detects the 500 GB NVMe.
- [ ] Virtualization is enabled.
- [ ] Ethernet link light is active.
- [ ] USB appears as a UEFI boot option.
- [ ] No unexplained BIOS password or hardware warning exists.

**Checkpoint:** Do not start installation if the drive capacity or identity differs from the inventory.
