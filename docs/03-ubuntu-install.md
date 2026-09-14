# 03 // Install Ubuntu Server 26.04.1 LTS

This installation targets the M720q's 500 GB NVMe and erases Windows.

## Installer walkthrough

1. Boot the verified Ubuntu USB using `F12`.
2. Select **Try or Install Ubuntu Server**.
3. Choose your language and keyboard layout.
4. Select the wired Ethernet interface.
5. Accept DHCP for the first installation.
6. Leave proxy blank unless your network requires one.
7. Use Ubuntu's default archive mirror.
8. Choose **Use an entire disk**.
9. Select only the confirmed 500 GB NVMe.
10. Keep the guided LVM layout for a simple, flexible first build.
11. Review the destructive storage summary carefully.
12. Confirm only after verifying the correct disk.

## Identity

Use:

| Field | Choice |
| --- | --- |
| Server name | `vision-node-01` |
| Username | A named admin account; do not use `root` |
| Password | Unique and stored in a password manager |

Do not put your real username, password, or email in this public repository.

## SSH and packages

1. Select **Install OpenSSH server**.
2. Import a GitHub SSH key only if you recognize and control it; otherwise add a key after installation.
3. Skip optional server snaps for the cleanest baseline.
4. Allow installation to complete.
5. Choose reboot.
6. Remove the USB when prompted, then press Enter.

## First login

Log in locally using the named administrator. The prompt should show the hostname `vision-node-01`.

Run:

```bash
hostnamectl
ip -br address
lsblk
free -h
```

Do not publish unredacted IP addresses, MAC addresses, UUIDs, or serial numbers.

**Success condition:** Ubuntu boots from NVMe, accepts the local login, detects wired networking, and reports the expected hardware.
