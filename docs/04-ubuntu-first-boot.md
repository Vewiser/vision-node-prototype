# 04 // Ubuntu Desktop First Boot and SSH

## 1. Confirm the visual baseline

- Open **Settings → System → About** and confirm the expected CPU, memory, and Ubuntu version.
- Confirm Wi-Fi reconnects automatically.
- Confirm the display uses a comfortable resolution and scaling.
- Open Terminal with `Ctrl+Alt+T`.

## 2. Update the system

Use **App Center/Software Updater** for visibility, then confirm through Terminal:

```bash
sudo apt update
sudo apt full-upgrade -y
sudo reboot
```

## 3. Install the basic tools

```bash
sudo apt install -y openssh-server curl git vim htop tmux tree unzip ufw smartmontools
sudo systemctl enable --now ssh
```

## 4. Create a stable local connection

Keep Ubuntu on DHCP and create a DHCP reservation in the router for the Wi-Fi adapter.

```bash
hostname -I
ip -br address
nmcli device status
```

Do not publish the real address or MAC address.

## 5. Configure SSH keys

On your Mac or trusted workstation:

```bash
ssh-keygen -t ed25519 -a 100
ssh-copy-id YOUR_USER@YOUR_PRIVATE_NODE_IP
```

Test in a second terminal before changing SSH settings:

```bash
ssh YOUR_USER@YOUR_PRIVATE_NODE_IP
```

Never copy or commit the private key.

## 6. Enable the firewall

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow OpenSSH
sudo ufw enable
sudo ufw status verbose
```

Do not forward port 22 through the router.

## 7. Inspect the baseline

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

Do not install Docker, cloud CLIs, dashboards, or virtual machines until updates, SSH, firewall behavior, Wi-Fi reconnection, two reboots, and a basic backup have been validated.
