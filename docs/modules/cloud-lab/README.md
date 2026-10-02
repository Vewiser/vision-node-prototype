# VISION NODE // Disposable Cloud Instance

The cloud instance extends the local Ubuntu Server node. It is a temporary engineering sandbox, not permanent production infrastructure.

## Purpose

Use it for:

- Linux administration away from home
- Terraform/OpenTofu practice
- Web server and API experiments
- GitHub Actions deployment practice
- Logs, monitoring, and backup exercises
- Comparing local and cloud networking

Do not use it as a publicly exposed vulnerable target.

## Provider-neutral first instance

| Setting | Beginner choice |
| --- | --- |
| OS | Ubuntu Server 26.04.1 LTS when the provider offers it; otherwise its current Ubuntu LTS image |
| Size | Small general-purpose instance |
| Authentication | SSH key; no password login where supported |
| Administrator | Named non-root user |
| Inbound traffic | Deny by default |
| SSH | Restricted to your current IP or trusted private access |
| Storage | Small disposable boot disk |
| Data | Synthetic/non-sensitive only |
| Lifetime | One session or one short project |

## Cost controls

1. Enable MFA on the cloud account.
2. Create a separate lab project or account boundary.
3. Configure budget alerts before launching.
4. Understand that a budget alert may not be a hard spending cap.
5. Tag the instance with owner, purpose, and deletion date.
6. Remember that stop is not the same as delete.
7. Destroy the instance and verify related disks, snapshots, and addresses are gone.

## First experiment

1. Create one Ubuntu instance manually.
2. Connect using an SSH key.
3. Update packages.
4. Install Git.
5. Clone this public repository.
6. Serve a simple static test page.
7. Record validation without publishing its live address.
8. Delete the instance and associated resources.
9. Verify billing and resource inventory are empty.
10. Repeat later using Terraform/OpenTofu.

## GitHub rule

Commit:

- Sanitized Terraform/OpenTofu
- README files and diagrams
- Validation commands
- Cost-control checklist
- Teardown proof without account identifiers

Never commit:

- Cloud access keys
- Private SSH keys
- Terraform state
- Account IDs
- Public IP addresses
- Tokens or credentials
