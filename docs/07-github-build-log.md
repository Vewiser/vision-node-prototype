# 07 // GitHub Build Log Workflow

The goal is to document decisions and proof—not publish every raw screen or command output.

## Milestone rhythm

For each build session:

1. **Intent** — state what you are changing.
2. **Before** — capture the known-good state.
3. **Action** — record concise steps and official references.
4. **Test** — show how success or failure was determined.
5. **Lesson** — explain what changed in your understanding.
6. **Next** — name one controlled milestone.
7. **Commit** — save a small, meaningful update.

## Entry template

```markdown
## YYYY-MM-DD // Milestone name

### Intent
What I planned to accomplish.

### Changes
- Change one
- Change two

### Validation
- Test:
- Expected:
- Result:

### Problems and fixes
What failed, why it failed, and what fixed it.

### Lessons
What I understand now that I did not understand before.

### Next
The next controlled milestone.
```

## Commit style

```text
docs: record M720q hardware baseline
build: install Ubuntu Server 26.04.1 LTS
security: enable SSH keys and UFW
network: validate Wi-Fi-only reboot
build: install Docker and Compose
cloud: document first disposable instance
backup: validate first restore
security: prove isolated lab network
```

## Proof without oversharing

Before committing screenshots or logs:

- Crop serial numbers and QR codes.
- Blur MAC addresses and real IPs.
- Hide usernames, email addresses, bookmarks, and notifications.
- Remove passwords, tokens, recovery codes, SSH private keys, and shell history.
- Check reflections and location metadata.

If a credential is exposed, revoke or rotate it immediately. Deleting it in a later commit does not remove it from Git history.

## Public narrative

**Beginning:** I turned a small office PC into my first Ubuntu server.

**Middle:** I learned each layer by building it—Linux, networking, containers, cloud, backups, and isolation.

**End:** Vision Node became a repeatable mini data center and proof that I can operate the systems behind modern apps and cloud services.

## Release milestones

- `v0.1` — Documentation foundation
- `v0.2` — Ubuntu installed and secured
- `v0.3` — Wi-Fi/headless operation validated
- `v0.4` — Docker service and restore test
- `v0.5` — Disposable cloud instance
- `v0.6` — KVM test VM
- `v0.7` — Isolated ethical-security lab
- `v1.0` — Repeatable Vision Node Prototype 01
