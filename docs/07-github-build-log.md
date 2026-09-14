# 07 // GitHub Build Log Workflow

The goal is to document decisions and proof—not publish every raw screen or command output.

## Milestone rhythm

For each build session:

1. **Intent** — state what you are changing.
2. **Before** — capture the known-good state.
3. **Action** — record concise steps and official references.
4. **Test** — show how success or failure was determined.
5. **Lesson** — explain what changed in your understanding.
6. **Next** — name one next milestone.
7. **Commit** — save a small, meaningful documentation update.

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

Use concise imperative messages:

```text
docs: record M720q hardware baseline
docs: complete Proxmox preflight
build: install Proxmox VE 9.2
build: create Vision Core VM
security: document management access controls
backup: validate first VM restore
```

## Image workflow

Store public images under `images/build-log/YYYY-MM-DD/`.

Before committing:

- Crop serial numbers and QR codes.
- Blur MAC addresses and private IPs.
- Hide browser bookmarks, usernames, email addresses, and notifications.
- Remove passwords, tokens, recovery codes, and terminal history.
- Check reflections in displays and glossy surfaces.
- Remove location metadata from exported images.
- Use descriptive filenames such as `m720q-mounted-front.jpg`.

Never rely only on `.gitignore` after a secret has already been committed. Git preserves history. If a credential is exposed, revoke or rotate it immediately before cleaning history.

## Suggested public narrative

**Beginning:** I built the physical prototype to understand infrastructure by operating it.

**Middle:** Each layer—firmware, virtualization, Linux, networking, recovery, automation—is installed and proven separately.

**End:** Vision Node becomes a repeatable compact lab and a living demonstration of systems architecture.

## Branches

For a solo build, keep the workflow simple:

- `main`: tested documentation and stable milestones
- Short-lived branches: substantial rewrites or automation experiments
- Pull requests: optional self-review checkpoint for risky configuration changes

## Release milestones

- `v0.1` — Documentation foundation
- `v0.2` — Proxmox installed and validated
- `v0.3` — Vision Core baseline
- `v0.4` — Independent backup and restore test
- `v0.5` — Network services
- `v0.6` — Remote access and monitoring
- `v0.7` — Segmented security lab
- `v1.0` — Repeatable Vision Node Prototype 01
