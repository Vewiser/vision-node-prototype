# 01 // KVM and libvirt Foundation

KVM keeps the cyber lab separate from Docker and normal Ubuntu services.

## Verify hardware support

```bash
lscpu | grep Virtualization
sudo apt update
sudo apt install -y cpu-checker
kvm-ok
```

Expected: hardware acceleration is available. Otherwise confirm Intel Virtualization Technology in BIOS.

## Install

Use current Ubuntu documentation as the authority for package names:

```bash
sudo apt install -y qemu-kvm libvirt-daemon-system libvirt-clients virtinst
sudo systemctl enable --now libvirtd
sudo systemctl status libvirtd --no-pager
sudo usermod -aG libvirt,kvm "$USER"
```

Log out and back in, then validate:

```bash
id
virsh list --all
```

Do not weaken libvirt socket permissions to suppress errors.

## Validation

- [ ] `kvm-ok` succeeds.
- [ ] `libvirtd` is active.
- [ ] Administrator belongs to `libvirt` and `kvm`.
- [ ] `virsh list --all` works without root.
- [ ] At least 150 GB remains free.

Cockpit is optional. If used, keep it on the trusted LAN or behind an SSH tunnel; never port-forward it.
