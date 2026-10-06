# 05 // Ubuntu Desktop Starter Stack

Install in stages. Use the visual desktop when it helps, but practice the command line so Ubuntu Server and Amazon EC2 feel familiar.

## Phase 0 — Learning system

Before each phase, use the [AI-Assisted Mastery Loop](modules/ai-mastery-loop/README.md):

1. Read one official source section.
2. Explain what you think it means.
3. Ask AI to identify gaps.
4. Pass a closed-book quiz.
5. Apply the principle in a safe lab.
6. Recover from one controlled failure.
7. Repeat without copied commands.
8. Record sanitized proof.

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

Install Docker Engine from Docker's official Ubuntu repository. Validate the installation, understand the Docker socket risk, and recreate one service from a reviewed Compose file.

## Phase 3 — First useful service

Start with one low-risk service:

1. **Uptime Kuma** — confirms whether internal services are reachable.
2. **Homepage** — optional private command dashboard.
3. **n8n** — automation experiments after backups are proven.
4. **Tailscale** — private remote access without router port forwarding.

Do not make the first node your only DNS path.

## Phase 4 — Local virtualization

After Ubuntu Desktop is stable, install KVM/libvirt and Virtual Machine Manager. The first guest should be a low-risk Ubuntu test VM using libvirt's default NAT network. Start with 2 vCPU and 4 GB RAM.

## Phase 5 — Amazon EC2 Linux Mastery

Complete the [Amazon EC2 Linux Mastery Lab](modules/aws-ec2-linux-lab/README.md):

- Ubuntu Server and Amazon Linux practice
- SSH and Session Manager
- Files, permissions, services, storage, networking, and logs
- CloudWatch monitoring
- Automation and recovery
- Complete teardown and Proof 002

Apply the AI loop to one Linux, one cloud, and one networking/automation topic to complete Proof 003.

## Upgrade paths

- [Ubuntu Server](future/ubuntu-server-upgrade-path.md) — lean headless operation after the Desktop build is reproducible
- [Proxmox](future/proxmox-upgrade-path.md) — multiple simultaneous VMs after the need and hardware are proven

## Learning target

At the end of Prototype 01, you should be able to explain and demonstrate:

- How Ubuntu runs applications and services
- How users, permissions, SSH, and firewall rules work
- How Docker differs from the host
- How a VM differs from a container
- How local Linux compares with EC2 Linux
- How Linux skills transfer between distributions
- How data is backed up and restored
- How to verify cloud-resource teardown
- How to use AI without surrendering judgment or independent skill
