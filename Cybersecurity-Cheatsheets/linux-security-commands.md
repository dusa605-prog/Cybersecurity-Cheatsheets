> This cheat sheet summarizes essential Linux security commands for system hardening, auditing, and user management. Created as part of my cybersecurity studies at Holyoke Community College.

# 🛡️ Linux Security Commands Cheat Sheet

## 🔐 User & Group Management
- `sudo adduser username` — Create new user
- `sudo passwd username` — Set user password
- `sudo usermod -aG groupname username` — Add user to group
- `groups username` — Show user’s groups

## 🔒 File Permissions
- `ls -l` — View file permissions
- `chmod 644 filename` — Set read/write for owner, read-only for others
- `chown user:group filename` — Change file owner/group
- `umask` — Show default permission mask

## 🧱 Firewall (UFW)
- `sudo ufw status` — Check firewall status
- `sudo ufw enable` — Enable firewall
- `sudo ufw allow 22` — Allow SSH
- `sudo ufw deny 80` — Block HTTP

## 🕵️‍♂️ Audit & Logs
- `sudo ausearch -x command` — Audit logs for a command
- `sudo auditctl -l` — List audit rules
- `journalctl -xe` — View system logs
- `last` — Show recent logins

## 🧼 Cleanup & Hardening
- `sudo apt purge packagename` — Remove package completely
- `sudo find / -name "filename"` — Locate sensitive files
- `sudo rkhunter --check` — Scan for rootkits
- `sudo lynis audit system` — Run security audit (if Lynis installed)

## 🔗 Network Security
- `netstat -tuln` — List open ports and listening services
- `ss -tuln` — Faster alternative to netstat
- `iptables -L` — List current firewall rules

## 🔑 SSH Hardening
- `sudo nano /etc/ssh/sshd_config` — Edit SSH config
- `PermitRootLogin no` — Disable root login
- `PasswordAuthentication no` — Enforce key-based auth
- `sudo systemctl restart sshd` — Apply changes

## 🧩 SELinux & AppArmor
- `sestatus` — Check SELinux status
- `getenforce` — Show current SELinux mode
- `aa-status` — Show AppArmor profile status
- `aa-enforce /path/to/profile` — Enforce AppArmor profile

## 🧾 File Integrity
- `aide --check` — Run AIDE integrity check
- `tripwire --check` — Run Tripwire scan
- `sha256sum filename` — Verify file hash

## 📦 Package Verification
- `dpkg -V packagename` — Verify Debian package integrity
- `rpm -V packagename` — Verify RPM package integrity
