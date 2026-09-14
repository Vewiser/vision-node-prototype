# 02 // Isolated Virtual Network

The cyber range uses a libvirt network with no forwarding element. This prevents intentional routing to the physical network.

## Example definition

Create a private local file named `vision-lab.xml`:

```xml
<network>
  <name>vision-lab</name>
  <bridge name="virbr20" stp="on" delay="0"/>
  <domain name="vision-lab.test"/>
  <ip address="192.0.2.1" netmask="255.255.255.0">
    <dhcp>
      <range start="192.0.2.100" end="192.0.2.200"/>
    </dhcp>
  </ip>
</network>
```

This is a public documentation example. Select an appropriate, non-conflicting private range for the actual isolated lab and record it privately.

Define and start it:

```bash
sudo virsh net-define vision-lab.xml
sudo virsh net-start vision-lab
sudo virsh net-autostart vision-lab
virsh net-info vision-lab
virsh net-dumpxml vision-lab
```

## Prove isolation

- [ ] No `forward` element exists.
- [ ] The bridge is not bound to physical Ethernet.
- [ ] No guest uses macvtap/direct or a physical bridge.
- [ ] Kali has one active NIC in lab mode.
- [ ] Target has one NIC on `vision-lab`.
- [ ] Target cannot reach the router or internet.
- [ ] Kali reaches only the intended lab target.
- [ ] Neither guest forwards packets.

Guest firewall rules are secondary. Correct virtual-network attachment is the primary boundary.
