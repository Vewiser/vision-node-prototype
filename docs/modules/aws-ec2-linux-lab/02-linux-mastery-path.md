# 02 // Linux Mastery Path

Complete these labs in order. Rebuild the instance whenever the environment becomes confusing. Repetition is part of the training.

## Level 1 — Orientation

Learn:

- Shell prompt, commands, flags, paths, and manual pages
- Root directory versus home directory
- Absolute versus relative paths
- Standard input, output, errors, pipes, and redirection

Practice:

```bash
pwd
ls -la
cd /
find /etc -maxdepth 1 -type f 2>/dev/null | head
man ls
printf 'vision-node\n' > practice.txt
cat practice.txt
```

Proof: explain `/`, `/home`, `/etc`, `/var`, `/tmp`, `/usr`, and `/opt` in plain language.

## Level 2 — Files, users, and permissions

Practice:

```bash
mkdir -p ~/labs/permissions
touch ~/labs/permissions/example.txt
ls -l ~/labs/permissions
id
getent group
sudo adduser labuser
sudo usermod -aG labuser labuser
sudo chown labuser:labuser ~/labs/permissions/example.txt
sudo chmod 640 ~/labs/permissions/example.txt
stat ~/labs/permissions/example.txt
```

Delete the disposable user when finished:

```bash
sudo deluser --remove-home labuser
```

Proof: explain owner, group, other, read, write, execute, `sudo`, and least privilege.

## Level 3 — Packages, processes, and services

Practice:

```bash
sudo apt update
apt list --upgradable
ps aux
top
systemctl --type=service --state=running
journalctl -p warning -b
```

Install a small service only after reviewing what it does:

```bash
sudo apt install -y nginx
systemctl status nginx
sudo ss -tulpn
curl http://localhost
```

Keep HTTP private unless a specific web-server lesson requires a temporary, narrowly scoped rule. Remove the service when finished:

```bash
sudo apt remove --purge -y nginx
sudo apt autoremove -y
```

Proof: identify the process, service unit, port, package, configuration, logs, and removal path.

## Level 4 — Storage and recovery

Use a separate disposable EBS volume.

1. Attach the volume in EC2.
2. Identify the new device carefully.
3. Format only the confirmed disposable device.
4. Create a mount point.
5. Mount it.
6. Create test data.
7. Record the filesystem UUID privately.
8. Unmount and detach it.
9. Reattach and restore access.
10. Delete it after the proof is complete.

Useful inspection commands:

```bash
lsblk -f
findmnt
df -h
du -sh /*
sudo blkid
```

Never copy a formatting command blindly. Device names can vary; selecting the wrong device destroys data.

Proof: explain volume, partition, filesystem, mount point, snapshot, backup, and restore.

## Level 5 — Networking and troubleshooting

Practice:

```bash
ip -br address
ip route
resolvectl status
ss -tulpn
curl -I https://example.com
dig example.com
ping -c 4 1.1.1.1
journalctl -u systemd-resolved --since today
```

Compare:

- Operating-system firewall
- EC2 security group
- Network ACL
- Public address
- Private address
- DNS name
- Route

Proof: diagnose one harmless connection failure created by removing or changing a lab rule, then restore the known-good configuration.

## Level 6 — Logs, monitoring, and health

Inspect locally:

```bash
journalctl -b
journalctl -p err
dmesg --level=err,warn
free -h
df -h
uptime
systemctl --failed
```

Then configure CloudWatch only after reviewing permissions and pricing. Collect a small, intentional set of metrics or logs; custom metrics and stored logs can create charges.

Proof: identify CPU, memory, disk, network, service, and authentication evidence and explain where each comes from.

## Level 7 — Automation

Rebuild a basic configuration with one of these:

1. cloud-init user data
2. A reviewed shell script
3. Ansible
4. Terraform/OpenTofu

The automation should:

- Update packages
- Create one non-root lab user
- Install one low-risk service
- Write a simple test page or file
- Enable the service
- Produce a validation result

Never put credentials inside user data, scripts, repositories, or Terraform state.

Proof: terminate the instance, create a fresh one, run the automation, and reproduce the expected result.

## Level 8 — Break and recover

Create only controlled, reversible failures:

- Stop a service and diagnose it
- Make a copy of a configuration, introduce one harmless error, then restore it
- Fill a small disposable test filesystem, then clear it
- Remove a temporary security-group rule and diagnose lost access from the local side
- Restore disposable data from a snapshot or rebuild it from code

Do not damage AWS control-plane access, root credentials, billing controls, or unrelated resources.

Proof: document symptom → evidence → cause → fix → validation → prevention.

## Level 9 — Distribution comparison

Repeat selected labs on Amazon Linux 2023.

Compare:

- Package manager and package names
- Default user
- Filesystem layout differences
- Service names
- Security defaults
- Update commands
- Cloud integration

Proof: create a one-page Ubuntu versus Amazon Linux field note without claiming one is universally better.

## Mastery gate

- [ ] Three clean instance launches
- [ ] Three clean teardowns
- [ ] SSH and Session Manager both understood
- [ ] Users and permissions lab passed
- [ ] Service lifecycle lab passed
- [ ] Storage attach/mount/detach lab passed
- [ ] Networking diagnosis passed
- [ ] Monitoring proof captured
- [ ] Automated rebuild passed
- [ ] Controlled recovery passed
- [ ] Ubuntu/Amazon Linux comparison completed
- [ ] No secret or live identifier committed
- [ ] Billing and resource inventory verified clean
