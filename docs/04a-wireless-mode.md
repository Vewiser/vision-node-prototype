# 04A // Direct Wi-Fi Vision Node Mode

Vision Node Prototype 01 uses the Lenovo M720q's internal Wi-Fi as its permanent primary connection. Temporary Ethernet is permitted for installation, driver recovery, or emergency maintenance.

## Before erasing Windows

Record the exact wireless-adapter model.

```powershell
Get-NetAdapter | Format-Table Name, InterfaceDescription, Status, LinkSpeed
```

Do not publish the MAC address, SSID, password, or real network address.

## Compatibility gate

Before relying on Wi-Fi:

- [ ] Exact Wi-Fi chipset is known.
- [ ] Ubuntu detects the adapter.
- [ ] The correct kernel driver loads.
- [ ] NetworkManager controls the interface.
- [ ] The node reconnects automatically after an unplugged reboot.
- [ ] Local console or temporary Ethernet recovery remains available.

## Install NetworkManager

Ubuntu Server may use Netplan with systemd-networkd by default. For this beginner build, NetworkManager provides a clearer Wi-Fi workflow.

```bash
sudo apt update
sudo apt install -y network-manager
sudo systemctl enable --now NetworkManager
```

Before changing Netplan, save a private copy of the current configuration:

```bash
sudo cp -a /etc/netplan /etc/netplan.backup
```

Netplan filenames and renderer settings vary. Review the active files before editing:

```bash
sudo ls -la /etc/netplan
sudo sed -n '1,200p' /etc/netplan/*.yaml
```

Set `renderer: NetworkManager` in the active Netplan configuration, then validate safely:

```bash
sudo netplan try
sudo netplan apply
```

Use the local console during this change so a network mistake does not lock you out.

## Identify and connect

```bash
lspci -nnk | grep -A3 -i network
ip link
nmcli device status
sudo nmtui
```

In `nmtui`:

1. Select **Activate a connection**.
2. Choose the intended Wi-Fi network.
3. Enter the password privately.
4. Save and exit.

Validate:

```bash
nmcli device status
ip -br address
ip route
ping -c 4 1.1.1.1
ping -c 4 example.com
```

## Wi-Fi-only reboot test

1. Reboot once with Ethernet connected.
2. Confirm Wi-Fi reconnects.
3. Shut down the M720q.
4. Disconnect Ethernet.
5. Boot using Wi-Fi only.
6. Confirm SSH, DNS, GitHub, and internet access.
7. Repeat the Wi-Fi-only reboot.
8. Create a DHCP reservation for the wireless adapter in the router.

Wireless mode passes only after two successful Wi-Fi-only boots.

## Virtual-machine networking

Begin with libvirt's default NAT network. Do not bridge vulnerable guests directly to the Wi-Fi interface or home LAN.

The ethical-hacking lab remains locked until:

- The VM network is isolated from the home LAN.
- Vulnerable targets cannot reach trusted devices.
- The operator can stop and remove the lab.
- A clean restore point exists.

## Reliability rules

- Prefer 5 GHz when signal quality is stable.
- Keep antennas clear of metal rack panels.
- Keep the Wi-Fi profile configured for automatic reconnection.
- Do not change the SSID or password without local-console access.
- Schedule large backups outside active work periods.
- Monitor packet loss and service availability.
- Do not expose SSH or service ports through the router.

## Acceptance checklist

- [ ] Adapter model recorded.
- [ ] Driver detected and loaded.
- [ ] Wi-Fi connects through NetworkManager.
- [ ] Two Wi-Fi-only boots succeed.
- [ ] SSH remains reachable.
- [ ] Router reservation works.
- [ ] Libvirt default NAT works.
- [ ] No public ports are exposed.
- [ ] Local recovery is available.

## Official references

- [Ubuntu networking documentation](https://documentation.ubuntu.com/server/explanation/networking/)
- [Netplan documentation](https://netplan.readthedocs.io/)
- [NetworkManager documentation](https://networkmanager.dev/docs/)
