# 04 // Omarchy to Cloud Workflow

Omarchy acts as the visual command console. The cloud instance is disposable Ubuntu infrastructure.

## Local tools

Install through Omarchy's supported package/menu workflow:

- Git and GitHub CLI
- SSH
- Docker
- Terraform or OpenTofu
- Provider CLI for the selected cloud
- VS Code, Cursor, or Neovim
- `btop`, `jq`, and terminal utilities

## First cloud experiment

1. Enable MFA on the cloud account.
2. Create a separate lab project/account boundary.
3. Configure billing alerts before compute.
4. Create one small Ubuntu LTS instance.
5. Use an SSH key and restrict inbound access.
6. Connect from Omarchy over Wi-Fi.
7. Clone the Vision Node repository.
8. Deploy a simple static page or API.
9. Record proof without publishing its address or account ID.
10. Destroy the instance, disk, snapshots, and unused public IP.
11. Verify the resource inventory and billing view.
12. Repeat later using Terraform/OpenTofu.

## GitHub flow

**Plan → Code → Verify → Review → Deploy → Observe → Record → Rollback**

Commit safe source files and documentation. Never commit cloud keys, private SSH keys, state files, account identifiers, live IPs, or tokens.

## Cost rule

Budget alerts are warnings and may not stop spending automatically. Every experiment needs an explicit teardown step and a deletion date.
