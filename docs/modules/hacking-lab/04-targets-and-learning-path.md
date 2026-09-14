# 04 // Targets and Defensive Learning Path

Start with web-application training. Add full vulnerable VMs only after isolation is proven.

## Target 1 — OWASP Juice Shop

OWASP Juice Shop is intentionally insecure and designed for legal training. Run it inside a disposable target VM attached only to `vision-lab`. Follow the official OWASP running guide and pin a known image version.

Learning objectives:

- HTTP requests and responses
- Authentication and sessions
- Input validation and access control
- Logging, evidence, and remediation

## Target 2 — Metasploitable

Rapid7 documents Metasploitable as an intentionally vulnerable test target. Treat it as hostile:

- Isolated network only
- No shared folders or personal credentials
- No physical USB devices or internet
- Powered off when unused
- Reset to baseline after training

## Progressive curriculum

### Level 1 — See the lab

Inventory only lab guests. Identify their addresses and expected services. Stop if any unexpected non-lab device appears.

### Level 2 — Understand the application

Use browser developer tools and an intercepting proxy inside Kali. Map requests, responses, cookies, headers, and error behavior.

### Level 3 — Validate vulnerable behavior

Follow an official training challenge. Capture minimal evidence. Explain why the weakness exists, the defensive fix, and how the fix would be tested.

### Level 4 — Blue-team replay

Review target logs, identify observable indicators, propose detection logic, reset the target, and confirm the mitigation.

## Journal template

```markdown
## Exercise

- Authorization:
- Systems in scope:
- Network mode:
- Learning objective:
- Expected behavior:
- Observation:
- Defensive lesson:
- Cleanup completed:
```

## Shutdown checklist

- [ ] Save sanitized notes.
- [ ] Shut down Kali and target.
- [ ] Restore the target when required.
- [ ] Confirm vulnerable guests do not autostart.
- [ ] Confirm no lab service listens on the physical LAN.
- [ ] Record the next defensive objective.

## Official references

- [Kali Linux documentation](https://www.kali.org/docs/)
- [OWASP Juice Shop running guide](https://pwning.owasp-juice.shop/companion-guide/latest/part1/running.html)
- [OWASP Vulnerable Web Applications Directory](https://vwad.owasp.org/)
- [Rapid7 Metasploitable 2](https://docs.rapid7.com/metasploit/metasploitable-2/)
