# 03 // Containers and Local VMs

## Docker

Omarchy lists Docker among its integrated development tools. Install it through the Omarchy menu or current official Omarchy method.

Validate:

```bash
docker --version
docker compose version
docker run --rm hello-world
```

Start with Uptime Kuma or another disposable, low-risk service. Identify its image, port, volume, backup, update, and removal paths before adding another container.

## Virtual machines

Omarchy provides an integrated Windows VM workflow through **Install → Windows**, implemented as a Docker VM. It is intended for productivity applications and does not provide GPU acceleration or passthrough.

For general Linux/Kali guests, use a supported KVM/libvirt manager only after confirming it coexists cleanly with Omarchy's current virtualization setup. Do not stack multiple competing VM managers without understanding their networks and storage.

## First VM

Use Ubuntu Server LTS:

| Setting | Value |
| --- | --- |
| vCPU | 2 |
| RAM | 4 GB |
| Disk | 50–60 GB |
| Network | NAT |
| Autostart | Off |
| Data | Disposable |

Practice create, boot, update, snapshot, stop, and delete before introducing Kali.

## 16 GB limit

Run one substantial VM at a time. Close heavy desktop applications and observe host memory before starting a guest:

```bash
free -h
btop
```

## Cyber-lab gate

A vulnerable guest must never use ordinary NAT, a physical bridge, or the home Wi-Fi network. Unlock the cyber lab only after a dedicated isolated virtual network passes the repository's isolation test.
