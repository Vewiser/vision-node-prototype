# 00 // Charter and Safety Gate

## Authorization gate

Before every exercise, identify the exact system in scope, confirm ownership or explicit authorization, verify its virtual network, define the stop condition, and define the restore method. If any answer is unclear, do not begin.

## Hard boundaries

- Never bridge an intentionally vulnerable guest to the physical LAN.
- Never place personal data, real passwords, or tokens in the lab.
- Never forward lab ports through the router.
- Never enable host shared folders for vulnerable targets.
- Never run denial-of-service exercises on the home network.
- Never test wireless networks you do not own and control.
- Never publish live credentials or weaponized payloads.

## Update mode

- Target VM: off
- Kali: default NAT only
- Purpose: verified updates and downloads
- End: shut Kali down and detach NAT

## Lab mode

- Kali and target: `vision-lab` only
- Internet and home LAN: unavailable
- End: save sanitized notes, shut down guests, restore target when required

## Escape response

If a target appears on the physical LAN or behaves unexpectedly, shut down both guests, disconnect M720q Ethernet if necessary, preserve non-sensitive logs, inspect interfaces and routes, and do not resume until isolation is proven.
