# 03 // Install ZimaOS

This is the beginner-friendly host installation for the Lenovo M720q. It erases the selected drive.

## Before starting

Use the current stable generic x86-64 image and current official ZimaOS installation guide. Do not rely on an old video when the official image format or installer has changed.

## Installation

1. Connect the M720q to the router/switch with Ethernet.
2. Attach keyboard, display, and verified ZimaOS installer.
3. Boot and press `F12`.
4. Select the UEFI entry for the installer.
5. Choose the 500 GB NVMe only after verifying its identity and capacity.
6. Confirm the destructive operation only after the Windows backup is proven.
7. Let installation finish without interrupting power.
8. Remove the installer and reboot from NVMe.

Exact screens can change by release. Record the installed ZimaOS version and any differences in the build log.

## First discovery

From a trusted device on the same LAN:

1. Check the local display for the node address or discovery instruction.
2. Use the official Zima client/discovery path or open the local address.
3. Complete initial account setup with a unique password.
4. Do not enable public sharing or router port forwarding.

## Success

- ZimaOS boots from NVMe.
- The dashboard loads locally.
- CPU, RAM, NVMe, and Ethernet are detected.
- The node survives a controlled reboot.
