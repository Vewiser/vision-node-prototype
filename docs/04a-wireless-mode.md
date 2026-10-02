# 04A // Direct Wi-Fi Vision Node Mode

Vision Node Prototype 01 uses the Lenovo M720q's internal Wi-Fi as its permanent primary connection. Ubuntu Desktop includes NetworkManager and a visual Wi-Fi settings panel, making this simpler than the later headless Server configuration.

Temporary Ethernet is permitted only for installation, driver recovery, or emergency maintenance.

## Before erasing Windows

Record the exact wireless-adapter model:

```powershell
Get-NetAdapter | Format-Table Name, InterfaceDescription, Status, LinkSpeed
```

Do not publish the MAC address, SSID, password, or real network address.

## Connect visually

1. Open the system menu in the top-right corner.
2. Select **Wi-Fi**.
3. Choose the intended 5 GHz network.
4. Enter the password privately.
5. Confirm **Connect automatically** is enabled.
6. Open **Settings → Wi-Fi** and confirm the connection remains active.

## Validate through Terminal

```bash
lspci -nnk | grep -A3 -i network
nmcli device status
ip -br address
ip route
ping -c 4 1.1.1.1
ping -c 4 example.com
```

## Wi-Fi-only reboot test

1. Confirm Wi-Fi works with Ethernet disconnected.
2. Reboot the M720q.
3. Confirm the desktop reconnects automatically.
4. Confirm SSH, DNS, GitHub, and internet access.
5. Shut down fully and start again.
6. Repeat the checks.
7. Create a DHCP reservation for the wireless adapter in the router.

Wireless mode passes only after two successful Wi-Fi-only boots.

## Virtual-machine networking

Begin with libvirt's default NAT network. Do not bridge vulnerable guests directly to Wi-Fi or the home LAN.

The ethical-security lab remains locked until:

- The VM network is isolated from the home LAN.
- Vulnerable targets cannot reach trusted devices.
- The operator can stop and remove the lab.
- A clean restore point exists.

## Reliability rules

- Prefer 5 GHz when signal quality is stable.
- Keep antennas clear of metal rack panels.
- Keep automatic reconnection enabled.
- Keep a keyboard, display, and temporary Ethernet cable available.
- Schedule large backups outside active work periods.
- Do not expose SSH or service ports through the router.

## Acceptance checklist

- [ ] Adapter model recorded.
- [ ] Wi-Fi connects through Ubuntu Desktop.
- [ ] Two Wi-Fi-only boots succeed.
- [ ] SSH remains reachable.
- [ ] Router reservation works.
- [ ] Libvirt default NAT works.
- [ ] No public ports are exposed.
- [ ] Local recovery is available.

## Official references

- [Ubuntu Desktop networking](https://documentation.ubuntu.com/desktop/en/latest/how-to/connect-to-the-internet/)
- [NetworkManager documentation](https://networkmanager.dev/docs/)
