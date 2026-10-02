# 05 // Ubuntu Desktop Starter Stack

Install in stages. Use the visual desktop when it helps, but practice the command line so the later Ubuntu Server path feels familiar.

## Phase 1 — Linux foundation

- OpenSSH Server
- Git
- curl
- vim
- htop
- tmux
- tree
- unzip
- UFW
- smartmontools

Practice:

```bash
pwd
ls -la
cd
mkdir
cp
mv
systemctl status ssh
journalctl -u ssh
df -h
free -h
git --version
```

## Phase 2 — Docker

Begin only after the first-boot, reboot, firewall, 48-hour stability, and backup checks pass.

Install Docker Engine from Docker's official Ubuntu repository:

- Docker Engine
- Docker CLI
- containerd
- Docker Buildx plugin
- Docker Compose plugin

Validate:

```bash
docker --version
docker compose version
sudo docker run --rm hello-world
```

Do not expose the Docker socket. Treat membership in the `docker` group as root-equivalent access.

## Phase 3 — First useful service

Start with one low-risk service:

1. **Uptime Kuma** — confirms whether internal services are reachable.
2. **Homepage** — optional private command dashboard.
3. **n8n** — automation experiments after backups are proven.
4. **Tailscale** — private remote access without router port forwarding.

Do not make the first node your only DNS path.

## Phase 4 — Local virtualization

After Ubuntu Desktop is stable, install KVM/libvirt and a visual manager such as Virtual Machine Manager.

```bash
lscpu | grep Virtualization
```

The first guest should be a low-risk Ubuntu test VM using libvirt's default NAT network. Start with 2 vCPU and 4 GB RAM. The vulnerable security lab remains locked until isolation is proven.

## Phase 5 — Cloud engineering

Use a separate sandbox cloud account or project with MFA and a small budget alert. Practice:

- Launching and destroying one Ubuntu instance
- SSH key authentication
- Firewall/security-group rules
- Terraform/OpenTofu state awareness
- Simple CI/CD
- Monitoring and logs
- Cost review and teardown

Cloud resources must be disposable and reproducible.

## Upgrade paths

- [Ubuntu Server](future/ubuntu-server-upgrade-path.md) — lean headless operation after the Desktop build is reproducible
- [Proxmox](future/proxmox-upgrade-path.md) — multiple simultaneous VMs after the need and hardware are proven

## Learning target

At the end of Prototype 01, you should be able to explain:

- How Ubuntu runs applications and services
- How the desktop relates to the Linux system underneath
- How users, permissions, SSH, and firewall rules work
- How Docker differs from the host
- How a VM differs from a container
- How a local node compares with a cloud instance
- Where data lives and how it is restored
- Why security-lab isolation matters
