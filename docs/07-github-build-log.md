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
build: install Ubuntu Desktop 26.04.1 LTS
security: enable SSH keys and UFW
network: validate Wi-Fi-only reboot
build: install Docker and Compose
proof: record first service restore
cloud: document first disposable instance
security: prove isolated lab network
```

## Public narrative

**Beginning:** I turned a small office PC into a visual Ubuntu workstation and mini data center.

**Middle:** I learned Linux, networking, containers, cloud, backups, and isolation one layer at a time.

**End:** I could operate the node from the terminal, rebuild its services, and decide whether to graduate it to Ubuntu Server.

## Release milestones

- `v0.1` — Documentation foundation
- `v0.2` — Ubuntu Desktop installed and secured
- `v0.3` — Wi-Fi and 48-hour baseline validated
- `v0.4` — Docker service, backup, and Proof 001
- `v0.5` — Disposable cloud instance
- `v0.6` — KVM test VM
- `v0.7` — Isolated ethical-security lab
- `v0.8` — Ubuntu Server migration decision
- `v1.0` — Repeatable Vision Node Prototype 01
