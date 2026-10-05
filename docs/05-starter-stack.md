# 05 // Ubuntu Desktop Starter Stack

Install in stages. Use the visual desktop when it helps, but practice the command line so Ubuntu Server and Amazon EC2 feel familiar.

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

## Phase 5 — Amazon EC2 Linux Mastery

Use a separate AWS lab identity with MFA, budget alerts, and tagged disposable resources.

Complete the [Amazon EC2 Linux Mastery Lab](modules/aws-ec2-linux-lab/README.md):

- Launch and connect to Ubuntu Server
- Learn files, users, permissions, packages, processes, services, storage, networking, and logs
- Practice SSH and Systems Manager Session Manager
- Add small, intentional CloudWatch monitoring
- Rebuild with cloud-init, Ansible, or Terraform/OpenTofu
- Compare Ubuntu Server with Amazon Linux 2023
- Complete a controlled break-and-recover exercise
- Terminate everything and document Proof 002

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
- How local Linux compares with EC2 Linux
- How Linux skills transfer between Ubuntu and Amazon Linux
- Where data lives and how it is restored
- How to prove that every cloud resource was removed
- Why security-lab isolation matters
