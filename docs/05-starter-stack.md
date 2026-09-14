# 05 // Starter Software Stack

Install in stages. The purpose is to understand each layer, not to fill the node with apps.

## Phase 1 — Linux foundation

Installed during first boot:

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

Begin only after the validation and backup checklist passes.

Install Docker Engine using Docker's current official Ubuntu instructions. Do not use random convenience scripts. Install:

- Docker Engine
- Docker CLI
- containerd
- Docker Compose plugin

Validate with the official hello-world container, then document installed versions:

```bash
docker --version
docker compose version
```

Do not publish Docker socket access to the network. Treat membership in the `docker` group as root-equivalent access.

## Phase 3 — First useful services

Add one service at a time:

1. **Uptime Kuma** — monitor whether your internal services are reachable.
2. **Homepage** — optional private dashboard.
3. **n8n** — automation experiments after backup procedures are proven.
4. **Tailscale** — private remote access; never publish authentication material.

Do not start with Pi-hole on the only stable DNS path. Introduce network-critical services after the server is reliable and you have a fallback.

## Not included yet

- Proxmox
- Kubernetes
- Kali Linux
- Public web hosting
- Router port forwarding
- Complex VLANs
- Databases containing important information
- Automatic scripts copied without review

These belong to later milestones.

## Learning target

At the end of Prototype 01, you should be able to explain:

- How Linux boots and runs services
- How users and permissions work
- How the server receives its address
- How SSH authentication works
- What a firewall rule allows
- How a container differs from the host
- Where data lives and how it is restored
