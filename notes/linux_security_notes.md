# Linux Security Notes (Beginner)

These are my beginner notes while learning Linux with a cybersecurity mindset.

---

## 1) Linux Directory Basics

- `/home` → where user files live
- `/etc` → system configuration files (very important for security)
- `/var/log` → logs live here (security monitoring)
- `/bin` and `/usr/bin` → system commands/programs
- `/tmp` → temporary files (sometimes abused by attackers)

---

## 2) Users & Identity

### Commands I practiced
- `whoami` → shows my current user
- `id` → shows UID, GID, groups
- `groups` → shows what groups my user belongs to

### Why this matters for security
Access in Linux depends heavily on:
- user identity
- group membership
- permissions

---

## 3) File Permissions (Core Security)

Example output from `ls -l`:

`-rw-r--r--`

Meaning:
- first `-` = file type
- next 3 = owner permissions
- next 3 = group permissions
- last 3 = others permissions

Permissions:
- `r` = read
- `w` = write
- `x` = execute

Security lesson:
✅ Misconfigured permissions can allow:
- unauthorized access
- data leaks
- privilege escalation

---

## 4) Important Commands

| Command | Why it matters |
|--------|-----------------|
| `ls -la` | view hidden files + permissions |
| `chmod` | change permissions |
| `chown` | change ownership |
| `cat` | view file content |
| `head` / `tail` | view top/bottom of files |
| `grep` | search inside files (log analysis skill) |

---

## 5) Logs & Monitoring (SOC mindset)

Logs are evidence.

Useful locations:
- `/var/log/auth.log` (authentication events)
- `/var/log/syslog` (system events)

Example search:
`grep "Failed password" /var/log/auth.log`

Security lesson:
✅ Logs help detect brute-force attempts, suspicious logins, and misconfigurations.

---

## Next Steps
- Add more notes weekly
- Practice reading auth logs
- Learn basic process monitoring: `ps`, `top`, `netstat`/`ss`
