# 01 // Preflight and Recovery

> Stop: installing ZimaOS on the selected 500 GB NVMe will erase Windows and its files.

## Preserve Windows

- [ ] Copy every required file to separate storage.
- [ ] Open several backed-up files from another computer.
- [ ] Confirm Windows activation/recovery information privately.
- [ ] Create Windows recovery media if you may restore it later.
- [ ] Confirm the M720q contains only the drive intended for erasure.

## Required equipment

- [ ] M720q and power adapter
- [ ] Keyboard and temporary display
- [ ] USB flash drive, 4 GB minimum; 8 GB or larger preferred
- [ ] Wired Ethernet cable
- [ ] Second computer for downloading and writing ZimaOS
- [ ] Independent backup destination
- [ ] Router administration access

## Compatibility

ZimaOS currently documents generic x86-64 installation with at least 25 GB of storage. The M720q's i5-8400T and 500 GB NVMe exceed that baseline. Keep Intel virtualization enabled for ZVM.

## Network plan

Use wired Ethernet and DHCP for the initial launch. After the node works, create a DHCP reservation in the router. Never publish the actual address, MAC address, router configuration, or remote-access credentials.

## Download safely

1. Download the current stable generic x86-64 ZimaOS image from the official ZimaOS site.
2. Read the current official installation guide because image format and flashing steps may change.
3. Verify a published checksum when ZimaOS supplies one.
4. Write the image using the official method or a trusted imaging utility.
5. Safely eject the USB.

## Go/no-go gate

- [ ] Windows backup verified
- [ ] Recovery decision complete
- [ ] Correct 500 GB NVMe identified
- [ ] Official ZimaOS image obtained
- [ ] Wired Ethernet connected
- [ ] Router access available
- [ ] Uninterrupted installation window available

Do not erase the disk until every item is complete.
