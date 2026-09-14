# 06 // First ZVM Virtual Machine

ZimaOS 1.3.0 introduced improved ZVM virtual-machine support. Treat it as an evolving feature and validate the current stable release before important use.

## First guest

Start with Ubuntu Server LTS—not Kali.

| Setting | Value |
| --- | --- |
| Name | `ubuntu-lab-01` |
| vCPU | 2 |
| RAM | 4 GB |
| Disk | 50–60 GB |
| Network | Default/NAT for initial learning |
| Autostart | Off |
| Data | Disposable only |

## Workflow

1. Enable Intel virtualization and VT-d in BIOS.
2. Open ZVM in the ZimaOS interface.
3. Upload a checksum-verified Ubuntu Server LTS ISO.
4. Create the VM using the resource limits above.
5. Install Ubuntu with a named administrator.
6. Update it and install Git.
7. Shut it down cleanly.
8. Create a snapshot/backup if ZVM supports the required operation in the installed release.
9. Practice start, stop, console access, and deletion.
10. Recreate it from documentation.

## 16 GB rule

Run one substantial guest at a time. Do not run Kali, an Ubuntu VM, and vulnerable targets together until RAM is upgraded and host memory has been measured.

## Isolation gate

Do not create an intentionally vulnerable target until you can prove ZVM offers a network with no route to:

- The physical home LAN
- The router
- The internet
- ZimaOS management services

If the installed ZVM release cannot prove this boundary, keep the hacking target off this node.
