# 02 // M720q BIOS Configuration

Firmware labels vary by BIOS revision. Record original values before changing them.

## Enter BIOS

1. Shut down the M720q.
2. Connect keyboard, display, Ethernet, and Ubuntu USB.
3. Power on and repeatedly press `F1` for Setup.
4. Use `F12` for the temporary boot menu.

## Recommended settings

| Setting | Target | Purpose |
| --- | --- | --- |
| Boot mode | UEFI | Modern Ubuntu boot |
| USB boot | Enabled | Run the installer |
| Intel Virtualization Technology | Enabled | Keeps Docker/VM options open |
| VT-d | Enabled | Future device and virtualization experiments |
| Secure Boot | Leave enabled initially | Ubuntu supports Secure Boot |
| Wake on LAN | Enabled | Future remote wake capability |
| After power loss | Power On or Last State | Automatic recovery |
| Date/time | Correct | Reliable updates, certificates, and logs |

If the installer fails to boot, troubleshoot the USB image and boot entry before changing Secure Boot. Do not enable Intel AMT unless you deliberately configure and secure it.

## Boot Ubuntu

1. Save BIOS settings and exit.
2. Press `F12` during restart.
3. Select the UEFI entry for the Ubuntu USB.
4. Confirm the Ubuntu Server installer appears.

## Validation

- [ ] BIOS detects 16 GB RAM.
- [ ] BIOS detects the 500 GB NVMe.
- [ ] Wired Ethernet link is active.
- [ ] USB appears as a UEFI boot option.
- [ ] No unexplained BIOS password or hardware warning exists.

**Checkpoint:** Stop if the displayed drive does not match the hardware inventory.
