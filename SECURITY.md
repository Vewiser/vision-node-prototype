# Security Policy

This is a public documentation repository for a private home lab, disposable cloud labs, and sanitized AI-assisted learning evidence.

## Never publish or paste into AI

- Passwords or password hashes
- API keys, access-key IDs, secret keys, tokens, cookies, or session data
- Private SSH keys
- Recovery codes or seed phrases
- Public IP addresses or public DNS names
- Exact private network topology or address assignments
- MAC addresses, serial numbers, UUIDs, or product keys
- AWS account, organization, instance, VPC, subnet, security-group, volume, snapshot, image, role, or resource IDs
- Terraform state or unredacted infrastructure plans
- Unredacted configurations, logs, terminal history, or screenshots
- Router, firewall, VPN, cloud, or identity-provider backups
- Client, patient, family, employee, or studio information
- Personal email addresses, physical addresses, location metadata, or billing details

## AI-assisted learning requirements

- Use synthetic examples and sanitized evidence.
- Make a first attempt before requesting a solution.
- Ask the AI to distinguish verified facts, inference, and uncertainty.
- Verify commands, versions, prices, security settings, and provider behavior through primary documentation.
- Run one unfamiliar command at a time.
- Understand the target before any delete, overwrite, recursive, privileged, network-exposing, or cost-creating command.
- Stop for human review before production changes, public exposure, spending changes, external messages, destructive actions, or security testing.
- AI output does not grant authorization to access or test any system.
- Document significant AI errors or limitations as part of Proof 003.

## Configuration examples

Use reserved documentation values:

- IPv4: `192.0.2.0/24`, `198.51.100.0/24`, or `203.0.113.0/24`
- Domains: `example.com`, `example.net`, or `example.org`
- Placeholder secrets: `REPLACE_ME`
- Resource identifiers: `RESOURCE_ID_REDACTED`

## Cloud-lab requirements

- Root or owner identities use MFA and are not used for normal labs.
- Use least-privilege lab roles or identities.
- Restrict SSH to the operator's current IP; remove the rule when not needed.
- Prefer managed session access after the SSH fundamentals lesson.
- Use synthetic data only.
- Tag disposable resources and set a planned deletion date.
- Verify current prices before use.
- Terminate compute and review storage, snapshots, addresses, monitoring, networking, and every region used.
- Never use a public cloud lab as an exposed vulnerable target.

## If a secret is exposed

1. Revoke or rotate it immediately.
2. Verify that the old credential no longer works.
3. Remove it from the current repository state.
4. Rewrite history if necessary.
5. Review access logs and connected systems.
6. Document the incident without republishing the secret.

Deleting a file in a later commit does not remove it from Git history.

## Ethical-use boundary

Security tools and experiments documented here are for systems owned by the operator or systems for which explicit authorization has been granted. This project does not authorize testing third-party systems.

## Reporting

Do not open a public issue containing a vulnerability, credential, real network information, cloud identifier, billing information, or personally identifiable information.
