# 03 // Install Ubuntu Desktop 26.04.1 LTS

This is the starting operating system for Vision Node Prototype 01. It gives the M720q a familiar visual interface while preserving the full Ubuntu terminal and engineering toolchain.

> Installing Ubuntu on the selected 500 GB NVMe will erase Windows and its files.

## Why Desktop first

- Visual settings make Wi-Fi, Bluetooth, displays, and updates easier to confirm.
- The Terminal teaches the same Linux commands used on Ubuntu Server.
- Docker, SSH, Git, KVM/libvirt, Terraform/OpenTofu, and cloud CLIs still work.
- The screen can become the local Vision Node command display.
- Ubuntu Server remains available as the later lean, headless upgrade path.

## Installer walkthrough

1. Boot the verified Ubuntu Desktop USB using `F12`.
2. Select **Try or Install Ubuntu**.
3. Use **Try Ubuntu** first if you want to test Wi-Fi, display, keyboard, and audio before erasing Windows.
4. Connect to the intended Wi-Fi network.
5. Start the installer.
6. Choose language, keyboard, and accessibility settings.
7. Choose the normal interactive installation.
8. Select only the confirmed 500 GB NVMe.
9. Choose **Erase disk and install Ubuntu** only after confirming the backup and correct drive.
10. Create a named administrator account with a unique password.
11. Set the computer name to `vision-node-01`.
12. Finish installation, reboot, and remove the USB when prompted.

## First login

Confirm the desktop loads, Wi-Fi reconnects, and the expected hardware appears.

Open Terminal with `Ctrl+Alt+T` and run:

```bash
hostnamectl
ip -br address
lscpu
lsblk
free -h
```

Do not publish real IP addresses, MAC addresses, UUIDs, serial numbers, usernames, or screenshots containing private information.

## Success condition

- Ubuntu Desktop boots from NVMe.
- The visual desktop is responsive.
- Wi-Fi and Bluetooth are detected.
- The system reports six CPU cores, approximately 16 GB RAM, and the expected NVMe.
- Terminal commands work.
- The node survives one controlled reboot.
