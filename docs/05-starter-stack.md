# 05 // Ubuntu Starter Stack

Install in stages. The point is to understand each layer, not fill the node with apps.

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

Begin only after the first-boot, reboot, firewall, and backup checks pass.

Install Docker Engine from Docker's current official Ubuntu repository:

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

## Phase 3 — First useful services

Add one service at a time:

1. **Uptime Kuma** — confirms whether internal services are reachable.
2. **Homepage** — optional private dashboard for the node.
3. **n8n** — local automation experiments after backups are proven.
4. **Tailscale** — private remote access without router port forwarding.

Do not make the first server your only DNS path. Network-critical services come later, with a fallback.

## Phase 4 — Local virtualization

After the Ubuntu host is stable, install KVM/libvirt using current Ubuntu guidance. Confirm CPU virtualization first:

```bash
lscpu | grep Virtualization
```

The first guest should be a low-risk Ubuntu test VM on libvirt's default NAT network. Start with 2 vCPU and 4 GB RAM. The vulnerable security lab remains locked until isolation is proven.

## Phase 5 — Cloud engineering

Use a separate sandbox cloud account or project with MFA and a small budget alert. Practice:

- Launching and destroying one Ubuntu instance
- SSH key authentication
- Security-group/firewall rules
- Terraform/OpenTofu state awareness
- Simple CI/CD
- Monitoring and logs
- Cost review and teardown

Cloud resources must be disposable and reproducible.

## Not included yet

- Proxmox
- Kubernetes
- Public production hosting
- Router port forwarding
- Complex VLANs
- Important databases without tested backups
- Scripts copied without review

## Learning target

At the end of Prototype 01, you should be able to explain:

- How Ubuntu boots and runs services
- How users, permissions, SSH, and firewall rules work
- How Docker differs from the host
- How a VM differs from a container
- How a local server compares with a cloud instance
- Where data lives and how it is restored
- Why security-lab isolation matters
