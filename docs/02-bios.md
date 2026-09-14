# 02 // M720q BIOS Configuration for ZimaOS

## Enter BIOS

1. Shut down the M720q.
2. Connect keyboard, display, Ethernet, and the ZimaOS installer.
3. Power on and repeatedly press `F1`.
4. Use `F12` for the temporary boot menu.

## Recommended settings

| Setting | Target | Purpose |
| --- | --- | --- |
| Boot mode | UEFI | Modern x86 boot |
| USB boot | Enabled | Start installer |
| Intel Virtualization Technology | Enabled | Required for hardware-assisted VMs |
| VT-d | Enabled | Keeps future VM/device options open |
| Wake on LAN | Enabled | Future remote wake |
| After power loss | Power On or Last State | Automatic recovery |
| Date/time | Correct | Reliable updates and certificates |

Follow the current ZimaOS guide for Secure Boot. If boot fails, verify the image and UEFI entry before changing security settings. Do not enable Intel AMT unless you deliberately secure it.

## Boot installer

1. Save and exit.
2. Press `F12`.
3. Select the UEFI USB entry.
4. Confirm the ZimaOS installer appears.

Stop if BIOS does not show 16 GB RAM or the expected 500 GB NVMe.
