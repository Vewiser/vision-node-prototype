# Security Policy

This is a public documentation repository for a private home lab.

## Never publish

- Passwords or password hashes
- API keys, access tokens, cookies, or session data
- Private SSH keys
- Recovery codes or seed phrases
- Public IP addresses
- Exact private network topology or address assignments
- MAC addresses, serial numbers, UUIDs, or product keys
- Unredacted configuration exports
- Router, firewall, VPN, or identity-provider backups
- Personal email addresses, physical addresses, or location metadata
- Screenshots containing notifications, bookmarks, reflections, or credentials

## Configuration examples

All public examples must use reserved documentation values such as:

- IPv4: `192.0.2.0/24`, `198.51.100.0/24`, or `203.0.113.0/24`
- Domains: `example.com`, `example.net`, or `example.org`
- Placeholder secrets: `REPLACE_ME`

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

Do not open a public issue containing a vulnerability, credential, real network information, or personally identifiable information.
