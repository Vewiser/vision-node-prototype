# 04A // Direct Wi-Fi Vision Node Mode

Vision Node Prototype 01 uses the Lenovo M720q's internal Wi-Fi as its permanent primary network connection. No mesh node or wireless bridge is part of this build.

Temporary Ethernet is permitted only for initial installation, driver recovery, or emergency maintenance.

## Before erasing Windows

Identify the exact adapter while Windows is still installed.

### PowerShell

```powershell
Get-NetAdapter | Format-Table Name, InterfaceDescription, Status, LinkSpeed
```

### Device Manager

Open **Device Manager → Network adapters** and record the full wireless-adapter name.

Document only the chipset/model. Do not publish the MAC address, SSID, password, or actual network address.

## Compatibility gate

ZimaOS officially documents command-line Wi-Fi configuration using `nmtui` on ZimaOS 1.4.2 and later for supported hardware such as the Intel AX210.

Before relying on wireless mode:

- [ ] Exact M720q Wi-Fi chipset is known.
- [ ] Installed ZimaOS version is 1.4.2 or newer.
- [ ] ZimaOS detects the adapter.
- [ ] The correct kernel driver loads.
- [ ] The node reconnects automatically after an unplugged reboot.

If the adapter is unsupported, stop and identify a ZimaOS-compatible internal replacement adapter. Do not redesign the build around a bridge.

## Initial installation

1. Connect temporary Ethernet.
2. Install the current stable ZimaOS image.
3. Complete initial account setup.
4. Install stable ZimaOS updates.
5. Confirm local-console access.
6. Identify the wireless adapter.
7. Configure Wi-Fi.
8. Test wireless reboot.
9. Remove Ethernet.

Do not place the node in its final headless location until the Wi-Fi-only reboot passes.

## Identify Wi-Fi inside ZimaOS

From Terminal or the local console:

```bash
lspci -nnk | grep -A3 -i network
ip link
nmcli device status
```

The adapter should appear as a wireless device rather than missing, unavailable, or unmanaged.

## Connect with NetworkManager

```bash
sudo nmtui
```

Then:

1. Select **Activate a connection**.
2. Select the intended Wi-Fi network.
3. Enter the password privately.
4. Save and exit.
5. Confirm connectivity.

```bash
nmcli device status
ip address
ip route
ping -c 4 1.1.1.1
ping -c 4 example.com
```

## Wi-Fi-only reboot test

1. Reboot once with Ethernet connected.
2. Confirm Wi-Fi reconnects.
3. Open the ZimaOS dashboard wirelessly.
4. Shut the M720q down.
5. Disconnect Ethernet.
6. Boot using Wi-Fi only.
7. Confirm dashboard, apps, DNS, GitHub, and cloud access.
8. Repeat the reboot once more.
9. Create a DHCP reservation for the wireless adapter in the router.

Wireless mode passes only after two successful Wi-Fi-only boots.

## Local VM networking

Use ZVM's default NAT mode for the first Ubuntu guest.

Avoid direct or bridged VM networking over the Wi-Fi interface. A Wi-Fi client does not behave like a normal Ethernet bridge, and support can vary by driver and ZVM release.

The hacking lab remains locked until ZVM provides and passes a separate isolated-network test. Host Wi-Fi access does not grant vulnerable targets permission to reach the home LAN.

## Reliability rules

- Use the 5 GHz band when signal quality is stable.
- Place the M720q where its antennas are not blocked by metal rack components.
- Avoid enclosing the Wi-Fi antennas behind solid metal panels.
- Keep the Wi-Fi profile configured for automatic reconnection.
- Do not change the SSID or password without local-console access.
- Schedule large backups outside active work periods.
- Monitor packet loss and dashboard availability with Uptime Kuma.
- Do not expose the dashboard or VM ports through the router.

## Expected tradeoffs

- Slower and less consistent transfers than Ethernet
- Higher latency under interference
- No dependable Wake-on-WLAN assumption
- Possible ZVM bridge limitations
- Recovery may require a keyboard, display, or temporary Ethernet
- Heavy NAS transfers may compete with VM and cloud traffic

## Recovery plan

Keep available:

- Keyboard and display
- Temporary Ethernet cable
- ZimaOS installer/recovery USB
- Private record of the Wi-Fi configuration
- Independent backup

## Acceptance checklist

- [ ] Adapter model recorded.
- [ ] Driver detected and loaded.
- [ ] Wi-Fi connects through `nmtui`.
- [ ] Two Wi-Fi-only boots succeed.
- [ ] Dashboard remains reachable.
- [ ] Router reservation works.
- [ ] First ZVM guest works through NAT.
- [ ] No public ports are exposed.
- [ ] Local recovery is available.

## Official references

- [Enable Intel AX210 Wi-Fi on ZimaOS](https://www.zimaspace.com/docs/hardware/enable-intel-ax210)
- [ZimaOS network configuration](https://www.zimaspace.com/docs/developer/networking)
- [ZimaOS remote access safety](https://www.zimaspace.com/docs/zimaos/remote-access)
