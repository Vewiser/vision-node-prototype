# 02 // M720q BIOS Configuration for Ubuntu Desktop

## Enter BIOS

1. Shut down the M720q.
2. Connect the keyboard, display, and Ubuntu Desktop installer USB.
3. Keep temporary Ethernet available for recovery, but it is not required when the internal Wi-Fi works in the live session.
4. Power on and repeatedly press `F1`.
5. Use `F12` for the temporary boot menu.

## Recommended settings

| Setting | Target | Purpose |
| --- | --- | --- |
| Boot mode | UEFI | Modern x86 boot |
| USB boot | Enabled | Start installer |
| Intel Virtualization Technology | Enabled | Required for KVM/libvirt |
| VT-d | Enabled | Keeps future VM/device options open |
| Wake on LAN | Optional | Useful only with Ethernet |
| After power loss | Power On or Last State | Automatic recovery |
| Date/time | Correct | Reliable updates and certificates |

Keep Secure Boot enabled initially because Ubuntu supports it. If the verified installer does not boot, confirm the ISO checksum and UEFI USB entry before changing security settings. Do not enable Intel AMT unless you deliberately configure and secure it.

## Boot installer

1. Save and exit.
2. Press `F12`.
3. Select the UEFI USB entry.
4. Choose **Try or Install Ubuntu**.
5. Use the live desktop to confirm Wi-Fi and display support before erasing Windows.

Stop if BIOS does not show 16 GB RAM or the expected 500 GB NVMe.
