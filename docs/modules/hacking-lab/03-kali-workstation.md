# 03 // Kali Workstation

Use Kali as a disposable testing workstation, not as the Ubuntu host OS.

## Source and resources

Download only from the official Kali website and verify the published checksum. Prefer the current installer ISO or official KVM-compatible image.

| Setting | Value |
| --- | --- |
| Name | `kali-lab-01` |
| vCPU | 2 |
| RAM | 4096 MB |
| Disk | 60 GB, qcow2 |
| Lab NIC | `vision-lab` |
| Shared folders | Disabled |

## Update mode

1. Confirm all vulnerable targets are off.
2. Shut Kali down.
3. Attach Kali only to libvirt's default NAT.
4. Boot, update from official repositories, and shut down.
5. Detach NAT.

## Lab mode

1. Confirm Kali has no NAT, physical bridge, or direct interface.
2. Attach Kali only to `vision-lab`.
3. Start the intended target.
4. Verify scope before assessment.

Never hot-add a second network for convenience.

## Clean baseline

After installation and updates, shut Kali down, copy or snapshot the clean disk, name it `kali-clean-baseline`, and record its version. Never commit VM disks or credentials.

## Route validation

```bash
ip -br address
ip route
```

In lab mode, no route should reach the physical LAN or internet. Redact addresses and MAC details before publishing.
