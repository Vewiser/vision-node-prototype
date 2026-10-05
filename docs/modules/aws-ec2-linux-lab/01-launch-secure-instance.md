# 01 // Launch a Secure EC2 Linux Practice Instance

## Before launch

1. Sign in with the lab identity, not the AWS root user.
2. Confirm MFA and budget alerts.
3. Open the EC2 console in the intended region.
4. Check current EC2, EBS, public IPv4, snapshot, CloudWatch, and data-transfer pricing.
5. Decide the end time for the session.

## Recommended first build

| Setting | Beginner choice |
| --- | --- |
| Name | `vision-node-ec2-linux-01` |
| Image | Current Ubuntu Server LTS image from the official publisher |
| Architecture | x86-64 for the simplest comparison with the M720q |
| Instance | Smallest currently eligible general-purpose size that meets the lab |
| Storage | Small disposable encrypted EBS root volume |
| Authentication | New lab-only SSH key or Session Manager |
| Network | Default VPC for the first fundamentals lab |
| Inbound | SSH from current IP only, or none when using Session Manager |
| Public services | None by default |
| Data | Synthetic and disposable only |

## Required tags

Use non-sensitive values:

- `Project=vision-node`
- `Module=ec2-linux-lab`
- `Environment=training`
- `Owner=operator`
- `DeleteAfter=YYYY-MM-DD`

## Connection option A — SSH lesson

AWS requires the instance to pass status checks, the private key to have appropriate permissions, and the security group to allow SSH from the connecting IP.

```bash
chmod 400 /private/path/vision-node-lab.pem
ssh -i /private/path/vision-node-lab.pem ubuntu@INSTANCE_PUBLIC_DNS
```

Replace the placeholders privately. Never commit the key, public DNS name, public IP, account ID, or instance ID.

After connecting:

```bash
whoami
hostnamectl
uname -a
ip -br address
lsblk
free -h
uptime
```

## Connection option B — Session Manager

After the SSH fundamentals lesson, configure the instance profile, Systems Manager Agent, and network access required by AWS Systems Manager. Session Manager can provide shell access without opening inbound SSH.

Validate the session, then remove the SSH inbound rule if it is no longer required.

## First security checks

```bash
sudo apt update
sudo apt full-upgrade -y
sudo ss -tulpn
sudo systemctl --failed
last
```

Review before installing anything else:

- Which ports are listening?
- Which security-group rules exist?
- Which user are you logged in as?
- Which commands require `sudo`?
- What changes after reboot?

## Launch proof

Record only sanitized evidence:

- Image family and distribution
- Instance family/size class
- Region name if you choose to publish it
- Successful connection method
- Package-update result
- Status-check result
- Start time and intended termination time
- No credentials or live network identifiers
