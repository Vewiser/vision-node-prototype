# 04 // ZimaOS First Boot

## First 30 minutes

1. Record the ZimaOS version.
2. Rename the device `vision-node-01`.
3. Install stable system updates.
4. Confirm the 500 GB NVMe and available space.
5. Confirm wired Ethernet is primary.
6. Create a DHCP reservation in the router.
7. Set a unique administrator password.
8. Keep remote public access disabled.
9. Reboot and confirm the dashboard returns.

## Storage rule

The single NVMe currently holds the OS, apps, data, and VM disks. It is not redundant. Do not store the only copy of family, studio, dental, financial, or client data on Prototype 01.

Suggested working budget:

| Use | Initial ceiling |
| --- | ---: |
| ZimaOS and updates | System-managed |
| Apps and app data | 100 GB |
| First ZVM guest | 60 GB |
| Second/disposable images | 60 GB |
| Free working reserve | At least 150 GB |

These are operating guardrails, not disk partitions.

## Security baseline

- Dashboard available only on trusted LAN
- No router port forwarding
- No default/reused password
- No secrets in GitHub screenshots
- No public file shares
- Separate cloud account and MFA
- Recovery path tested locally

Stop before apps if basic storage, networking, updates, or reboot are unreliable.
