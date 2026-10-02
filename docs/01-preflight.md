# 01 // Preflight and Recovery

> Stop: installing Ubuntu Desktop on the selected 500 GB NVMe will erase Windows and its files.

## Preserve Windows

- [ ] Copy every required file to separate storage.
- [ ] Open several backed-up files from another computer.
- [ ] Confirm Windows activation and recovery information privately.
- [ ] Create Windows recovery media if you may restore it later.
- [ ] Confirm the M720q contains only the drive intended for erasure.

## Required equipment

- [ ] M720q and power adapter
- [ ] Keyboard, mouse, and display
- [ ] USB flash drive, 8 GB or larger
- [ ] Temporary Ethernet cable for recovery if needed
- [ ] Second computer for downloading and writing the installer
- [ ] Independent backup destination
- [ ] Router administration access

## Compatibility

Ubuntu Desktop 26.04.1 LTS requires a 64-bit Intel/AMD processor, 6 GB RAM, and 25 GB free storage. The M720q's Intel Core i5-8400T, 16 GB RAM, and 500 GB NVMe exceed that baseline. Keep Intel virtualization enabled for the later KVM/libvirt lab.

## Try-before-install gate

Boot the USB into **Try Ubuntu** and confirm:

- [ ] Display and keyboard work.
- [ ] Internal Wi-Fi sees the intended network.
- [ ] Bluetooth is detected if required.
- [ ] The NVMe appears.
- [ ] The desktop is responsive.

## Download safely

1. Download Ubuntu Desktop 26.04.1 LTS for Intel/AMD 64-bit systems from the official Ubuntu site.
2. Read the current official installation guide.
3. Verify the published SHA256 checksum.
4. Write the ISO with a trusted imaging utility.
5. Safely eject the USB.

## Go/no-go gate

- [ ] Windows backup verified
- [ ] Recovery decision complete
- [ ] Correct 500 GB NVMe identified
- [ ] Official Ubuntu Desktop ISO obtained
- [ ] SHA256 checksum verified
- [ ] Live-session hardware test passed
- [ ] Router access available
- [ ] Uninterrupted installation window available

Do not erase the disk until every item is complete.
