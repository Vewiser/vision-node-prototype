# 01 // Install Omarchy

> A full-disk installation erases the selected 500 GB NVMe. The official installer enables full-disk encryption by default.

## Before installation

- [ ] Back up every required Windows file.
- [ ] Save the Windows/BitLocker recovery information privately.
- [ ] Use a wired keyboard or 2.4 GHz receiver keyboard.
- [ ] Download the current Omarchy ISO only from the official site.
- [ ] Write it with Balena Etcher on macOS/Windows or the official recommended tool.
- [ ] Verify the download using the integrity method published with the current release.
- [ ] Confirm the target is the 500 GB NVMe.

## BIOS

The current Omarchy manual requires:

- UEFI boot
- Secure Boot disabled
- TPM disabled when required by the installer
- Intel virtualization enabled
- VT-d enabled
- USB boot enabled

Disabling TPM or Secure Boot can affect the existing Windows/BitLocker installation. Complete backup and recovery-key capture before changing either.

## Installation

1. Insert the Omarchy USB.
2. Power on and press `F12`.
3. Select the UEFI USB entry.
4. Connect to Wi-Fi when prompted.
5. Choose the full-disk option only after confirming the correct NVMe.
6. Choose a strong encryption password stored in a password manager.
7. Complete the installer questions.
8. Remove the USB and reboot.
9. Enter the disk-encryption password using the wired/2.4 GHz keyboard.
10. Complete first login.

## First controls

Omarchy is keyboard-first:

- `Super + Space`: application launcher
- `Super + Alt + Space`: Omarchy menu
- `Super + Return`: terminal
- `Super + Shift + Return`: browser

## Baseline

Before adding apps or VMs:

1. Apply stable Omarchy updates through its documented update flow.
2. Confirm Wi-Fi, audio, display, sleep settings, and time.
3. Confirm Git works.
4. Reboot twice.
5. Record the installed version.
6. Create the first system snapshot using Omarchy's current documented feature.

Do not install Kali, vulnerable targets, or critical services during the baseline session.

## Official references

- [Omarchy Getting Started](https://omarchy.org/manual/getting-started/)
- [Omarchy Manual](https://omarchy.org/manual/)
- [Official Omarchy repository](https://github.com/omacom/omarchy)
