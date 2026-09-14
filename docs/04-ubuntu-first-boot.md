# 04 // Ubuntu First Boot and SSH

## 1. Update the system

```bash
sudo apt update
sudo apt full-upgrade -y
sudo reboot
```

Log back in after reboot.

## 2. Install the basic tools

```bash
sudo apt install -y curl git vim htop tmux tree unzip ufw smartmontools
```

These provide downloads, version control, editing, monitoring, persistent terminal sessions, archive handling, a firewall, and drive-health tools.

## 3. Give the node a stable address

Keep Ubuntu on DHCP and create a DHCP reservation in the router using the wired adapter. This is simpler to recover than manually editing network configuration during Prototype 01.

Confirm the address privately:

```bash
hostname -I
ip -br address
```

## 4. Configure SSH keys

On your Mac or trusted workstation:

```bash
ssh-keygen -t ed25519 -a 100
ssh-copy-id YOUR_USER@YOUR_PRIVATE_SERVER_IP
```

If `ssh-copy-id` is unavailable, securely add the contents of your **public** `.pub` key to `~/.ssh/authorized_keys` on the server.

Test in a second terminal before changing SSH settings:

```bash
ssh YOUR_USER@YOUR_PRIVATE_SERVER_IP
```

Never copy or commit the private key.

## 5. Enable the firewall

First confirm SSH works locally, then:

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow OpenSSH
sudo ufw enable
sudo ufw status verbose
```

Keep your local console connected while testing so you can recover from a mistake. Do not forward port 22 through the router.

## 6. Inspect the baseline

```bash
hostnamectl
lscpu
free -h
lsblk
df -h
systemctl --failed
sudo smartctl --scan
```

## Stop point

Do not install Docker or dashboards until updates, SSH, firewall behavior, reboot, and a basic backup have all been validated.
