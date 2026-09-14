# Changelog

All notable Vision Node milestones are documented here.

## [Unreleased]

### Planned

- Complete Windows backup and recovery checkpoint
- Install Ubuntu Server 26.04.1 LTS directly on the M720q
- Configure SSH and basic firewall
- Validate independent backup and restore
- Add Docker only after the Linux baseline passes
- Confirm switch and Raspberry Pi specifications

## [0.2.0] - 2026-09-14

### Changed

- Simplified Prototype 01 from Proxmox virtualization to bare-metal Ubuntu Server
- Reframed the node around foundational Linux, networking, SSH, Git, containers, and backups
- Moved Proxmox to a future upgrade path
- Replaced VM-specific installation steps with a direct Ubuntu runbook

## [0.1.0] - 2026-09-14

### Added

- M720q hardware baseline
- Initial virtualization architecture
- Destructive-install preflight
- BIOS checklist
- Validation and backup gates
- Public GitHub build-log workflow
- Repository security policy
