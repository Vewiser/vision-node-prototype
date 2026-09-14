# 05 // Create Vision Core

Vision Core is the first Ubuntu Server VM. It establishes the reusable Linux environment before Docker, automation, or security tooling is introduced.

## VM specification

| Setting | Value |
| --- | --- |
| VM ID | 100 |
| Name | `vision-core-01` |
| OS | Ubuntu Server 26.04.1 LTS, x86-64 |
| Machine/BIOS | Proxmox defaults for a modern Linux guest |
| SCSI controller | VirtIO SCSI single |
| Disk | 80 GB on `local-lvm`; discard enabled if supported |
| CPU type | `host` for this single-node lab |
| Sockets/cores | 1 socket, 4 cores |
| RAM | 6144 MB |
| Ballooning | Minimum 4096 MB; monitor before relying on it |
| Network | VirtIO bridged to `vmbr0` |
| Start at boot | Enable after validation |
| QEMU guest agent | Enable after installing agent in guest |

## Create the VM

1. Click **Create VM**.
2. Use VM ID 100 and name `vision-core-01`.
3. Attach the verified Ubuntu Server ISO.
4. Retain compatible system defaults; enable QEMU guest agent support.
5. Create an 80 GB SCSI disk on `local-lvm`.
6. Assign 4 CPU cores with CPU type `host`.
7. Assign 6144 MB RAM.
8. Attach one VirtIO network adapter to `vmbr0`.
9. Review the summary before finishing.
10. Start the VM and open its console.

## Install Ubuntu

1. Select the default Ubuntu Server installation.
2. Choose language and keyboard.
3. Use DHCP during installation unless you already maintain a tested reservation.
4. Use the entire 80 GB virtual disk with the guided LVM layout.
5. Set hostname to `vision-core-01`.
6. Create a named non-root administrator.
7. Store its unique password in a password manager.
8. Install OpenSSH Server.
9. Do not import unknown SSH keys.
10. Skip optional snaps/packages during the first baseline build.
11. Finish installation, reboot, and detach the ISO if necessary.

## First update

Log in through the console:

```bash
sudo apt update
sudo apt full-upgrade -y
sudo apt install -y qemu-guest-agent curl git
sudo systemctl enable --now qemu-guest-agent
sudo reboot
```

After reboot:

```bash
hostnamectl
ip -br address
systemctl status qemu-guest-agent --no-pager
```

Redact network details before publishing output.

## SSH setup

From your trusted workstation, create a modern SSH key if you do not have a suitable one:

```bash
ssh-keygen -t ed25519 -a 100
```

Copy only the public key to the VM. Never commit the private key.

After confirming key-based login in a second terminal, review SSH hardening. Do not disable password or root recovery paths until the key login is proven.

## Baseline snapshot

1. Shut down the VM cleanly.
2. Create snapshot `baseline-clean-install`.
3. Add description: Ubuntu installed, updated, guest agent active; no application stack.
4. Start the VM and validate networking again.

A snapshot is not a backup. It lives on the same NVMe and cannot recover from drive failure.

## Stop point

Do not install Docker, Portainer, n8n, databases, Pi-hole, Tailscale, Kubernetes, or Kali yet. First complete the validation and independent-backup milestone.
