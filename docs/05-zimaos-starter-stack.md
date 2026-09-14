# 05 // ZimaOS Starter Stack

Install one app at a time and document what it does, where its data lives, and how it is removed.

## Wave 1

1. **File Browser / Files** — learn storage and permissions.
2. **Uptime Kuma** — monitor only your own node and services.
3. **Dozzle or equivalent log viewer** — understand app logs.
4. **n8n later** — automation only after backups work.

Do not make a password manager, DNS server, public website, or irreplaceable photo archive the first experiment.

## App checklist

For every app:

- [ ] Source is trusted.
- [ ] Purpose is defined.
- [ ] Ports are recorded privately.
- [ ] Data directory is identified.
- [ ] No unnecessary public exposure exists.
- [ ] Backup method is known.
- [ ] Stop/start works.
- [ ] Removal is understood.
- [ ] GitHub build log is updated.

## Container lesson

ZimaOS makes apps easy, but they are still containers. Learn these four ideas:

- Image: the packaged application
- Container: the running instance
- Port: how you reach it
- Volume: where persistent data survives replacement

Ease of installation does not replace backup, access control, or update discipline.
