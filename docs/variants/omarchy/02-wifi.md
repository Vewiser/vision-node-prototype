# 02 // Wi-Fi-Only Operation

This edition uses the M720q internal Wi-Fi as its permanent network connection. Ethernet is not part of daily operation.

## Identify the adapter before erasing Windows

```powershell
Get-NetAdapter | Format-Table Name, InterfaceDescription, Status, LinkSpeed
```

Record only the chipset model publicly.

## Installer Wi-Fi

The Omarchy manual's Arch-based workflow supports Wi-Fi during installation. If a manual connection is required:

```text
iwctl
station wlan0 scan
station wlan0 get-networks
station wlan0 connect YOUR_NETWORK
```

The actual interface might not be named `wlan0`. Use the detected wireless device.

## After installation

Use Omarchy's NetworkManager interface to connect and save the Wi-Fi profile. Verify:

```bash
nmcli device status
nmcli connection show
ip route
ping -c 4 example.com
```

Never commit the SSID, password, MAC address, or actual IP.

## Acceptance test

- [ ] Exact Wi-Fi chipset is detected.
- [ ] Correct driver is loaded.
- [ ] 5 GHz network connects.
- [ ] Connection returns after two cold boots.
- [ ] GitHub and cloud SSH connections work.
- [ ] Docker can pull a harmless test image.
- [ ] Local VM reaches the internet through NAT.
- [ ] No public inbound ports are configured.

## Physical placement

Keep the M720q antennas clear of metal rack plates and dense cable bundles. Test signal quality in the final rack position before considering the build complete.

## Recovery

Maintain a wired/2.4 GHz keyboard, display, installer USB, and private Wi-Fi configuration record. A temporary Ethernet cable may be kept only as emergency recovery equipment.
