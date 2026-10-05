# VISION NODE // Disposable Cloud Lab

The cloud lab extends the local Ubuntu Desktop node with temporary remote infrastructure. It is for learning cloud engineering—not permanent production and never a publicly exposed vulnerable target.

## Current provider path

Amazon EC2 is the first detailed provider module:

- [Amazon EC2 Linux Mastery Lab](../aws-ec2-linux-lab/README.md)

The skills remain portable: secure access, Linux administration, cost controls, monitoring, automation, recovery, and complete teardown.

## Purpose

Use disposable cloud resources for:

- Linux administration away from home
- Terraform/OpenTofu practice
- Web server and API experiments
- GitHub Actions deployment practice
- Logs, monitoring, and backup exercises
- Comparing local desktop, local services, and cloud networking

## Provider-neutral rules

| Setting | Beginner choice |
| --- | --- |
| OS | Current supported Linux image from an official publisher |
| Size | Small general-purpose instance |
| Authentication | SSH key or provider-managed session access |
| Administrator | Named non-root user |
| Inbound traffic | Deny by default |
| SSH | Current IP only when required |
| Storage | Small encrypted disposable disk |
| Data | Synthetic/non-sensitive only |
| Lifetime | One session or one short project |

## Cost controls

1. Enable MFA.
2. Use a separate lab identity, project, or account boundary.
3. Configure daily and monthly budget alerts before launching.
4. Treat budget alerts as delayed warnings—not hard spending caps.
5. Tag every resource with owner, purpose, and deletion date.
6. Verify current compute, storage, address, monitoring, and transfer prices.
7. Remember that stop is not the same as delete.
8. Verify related disks, snapshots, addresses, logs, and networking resources are removed.

## GitHub rule

Commit:

- Sanitized infrastructure code
- README files and diagrams
- Validation commands
- Cost-control checklists
- Teardown proof without account identifiers

Never commit:

- Cloud access keys or session tokens
- Private SSH keys
- Terraform state
- Account or resource IDs
- Public IP addresses or DNS names
- Credentials or private billing information
