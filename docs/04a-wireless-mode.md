# 04A // Wireless Vision Node Mode

Yes, Vision Node can run over Wi-Fi after initial setup, provided ZimaOS recognizes the M720q wireless adapter.

## Recommended order

1. Install and update ZimaOS using temporary wired Ethernet.
2. Identify and test the internal Wi-Fi adapter.
3. Configure Wi-Fi with `nmtui`.
4. Confirm automatic reconnection after reboot.
5. Create a router reservation for the wireless adapter.
6. Disconnect Ethernet only after the wireless recovery test passes.

## Option A — Wireless bridge or mesh node

**Recommended for an always-on node.**

Place a compatible mesh satellite, travel router in bridge/client mode, or wireless bridge near Vision Node. Connect its LAN port to the M720q with a short Ethernet cable.

Benefits:

- ZimaOS continues to see a normal Ethernet connection.
- Better compatibility with dashboards, containers, and VMs.
- Easier recovery and fewer Linux Wi-Fi driver problems.
- More predictable operation than bridging VM traffic through a Wi-Fi client.
- The main router can remain in its inconvenient location.

The link between rooms is still wireless; only the final few inches use Ethernet.

## Option B — Internal M720q Wi-Fi

### Confirm the adapter

From ZimaOS Terminal or a local console:

```bash
lspci -nnk | grep -A3 -i network
ip link
nmcli device status
```

Record the chipset model, not the MAC address, in the public build log.

ZimaOS officially documents command-line Wi-Fi configuration with `nmtui` for supported Intel hardware on ZimaOS 1.4.2 and later.

### Connect

```bash
sudo nmtui
```

Then:

1. Select **Activate a connection**.
2. Select the intended Wi-Fi network.
3. Enter the password privately.
4. Save and exit.
5. Verify connectivity.

```bash
nmcli device status
ip address
ip route
ping -c 4 1.1.1.1
ping -c 4 example.com
```

Never copy SSIDs, passwords, MAC addresses, or actual private addresses into GitHub.

## Reboot test

1. Keep temporary Ethernet connected during initial configuration.
2. Reboot ZimaOS.
3. Confirm Wi-Fi reconnects automatically.
4. Open the dashboard from another trusted device.
5. Shut down.
6. Disconnect Ethernet.
7. Boot again.
8. Confirm the dashboard, apps, DNS, and cloud access work through Wi-Fi.
9. Confirm local keyboard/display recovery remains available.

Do not declare wireless mode complete until the unplugged reboot passes.

## VM rule

Use NAT for the first ZVM guest. Wi-Fi client interfaces often do not behave like Ethernet bridges, so avoid direct/bridged VM networking until ZimaOS explicitly supports and the lab proves it.

The vulnerable cyber-lab target remains locked until an isolated virtual network is verified. Wi-Fi connectivity does not replace lab isolation.

## Limitations

- Lower consistency and higher latency than Ethernet
- Reduced file-transfer performance under interference
- Wi-Fi driver compatibility depends on the exact adapter
- Wake-on-LAN usually does not work over ordinary Wi-Fi
- A changed SSID/password can strand a headless server
- VM bridge behavior may be limited
- Heavy NAS backups may take significantly longer

## Recovery kit

Keep one of these available:

- Temporary long Ethernet cable
- USB-to-Ethernet adapter supported by ZimaOS
- Keyboard and display
- Wireless bridge/mesh node

## Acceptance checklist

- [ ] Adapter chipset is identified.
- [ ] ZimaOS recognizes the wireless interface.
- [ ] Wi-Fi auto-connects after reboot.
- [ ] Dashboard loads with Ethernet unplugged.
- [ ] Router reservation uses the Wi-Fi adapter privately.
- [ ] Apps remain reachable.
- [ ] One ZVM guest works through NAT.
- [ ] No public dashboard or VM ports are exposed.
- [ ] Wired/local recovery remains possible.

## Official references

- [Enable Intel AX210 Wi-Fi on ZimaOS](https://www.zimaspace.com/docs/hardware/enable-intel-ax210)
- [ZimaOS network configuration](https://www.zimaspace.com/docs/developer/networking)
- [ZimaOS remote access safety](https://www.zimaspace.com/docs/zimaos/remote-access)
