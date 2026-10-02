# 01 // Preflight and Recovery

> Stop: installing Ubuntu Server on the selected 500 GB NVMe will erase Windows and its files.

## Preserve Windows

- [ ] Copy every required file to separate storage.
- [ ] Open several backed-up files from another computer.
- [ ] Confirm Windows activation and recovery information privately.
- [ ] Create Windows recovery media if you may restore it later.
- [ ] Confirm the M720q contains only the drive intended for erasure.

## Required equipment

- [ ] M720q and power adapter
- [ ] Keyboard and temporary display
- [ ] USB flash drive, 8 GB or larger
- [ ] Temporary Ethernet cable for the easiest first installation
- [ ] Second computer for downloading and writing the installer
- [ ] Independent backup destination
- [ ] Router administration access

## Compatibility

Ubuntu Server 26.04.1 LTS supports 64-bit Intel/AMD systems. The M720q's Intel Core i5-8400T, 16 GB RAM, and 500 GB NVMe exceed the installation baseline. Keep Intel virtualization enabled for the later KVM/libvirt lab.

## Network plan

Use Ethernet and DHCP during installation when practical. After Ubuntu is stable, validate the internal Wi-Fi, test two Wi-Fi-only reboots, and create a router-side DHCP reservation. Never publish the real address, MAC address, SSID, or router configuration.

## Download safely

1. Download the current Ubuntu Server 26.04.1 LTS AMD64 ISO from the official Ubuntu site.
2. Read the current official installation guide.
3. Verify the published SHA256 checksum.
4. Write the ISO with a trusted imaging utility.
5. Safely eject the USB.

## Go/no-go gate

- [ ] Windows backup verified
- [ ] Recovery decision complete
- [ ] Correct 500 GB NVMe identified
- [ ] Official Ubuntu Server ISO obtained
- [ ] SHA256 checksum verified
- [ ] Temporary network path available
- [ ] Router access available
- [ ] Uninterrupted installation window available

Do not erase the disk until every item is complete.
