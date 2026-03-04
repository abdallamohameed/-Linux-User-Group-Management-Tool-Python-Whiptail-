# Linux-User-Group-Management-Tool-Python-Whiptail

A simple interactive **TUI (Terminal UI)** tool for Linux system administration tasks.
It helps you manage **users** and **groups** using a clean menu interface built with **whiptail**, powered by Python.

> ⚠️ This tool must be run as **root** because it executes system administration commands like `useradd`, `usermod`, `groupadd`, etc.

---

## Features

### User Management
- ✅ Add a new user (wizard)
  - Optional comment (`-c`)
  - Create home directory (`-m`)
  - Optional shell (`-s`)
  - Set password
  - Final options:
    - Set primary group (`-g`)
    - Add secondary groups (`-aG`)
    - Set custom UID (`-u`)
- ✅ Modify existing user
  - Change shell (`-s`)
  - Change comment (`-c`)
  - Change home directory (`-d`)
  - Rename user (`-l`)
  - Add to secondary group (`-aG`)
  - Override secondary groups (`-G`)
  - Remove from group (`gpasswd -d`)
  - Show user info (`id`)
- ✅ Delete user (with optional home removal `userdel -r`)
- ✅ List users
  - Normal users only (UID ≥ 1000)
  - All users (root only)
- ✅ Disable (lock) user (`usermod -L`)
- ✅ Enable (unlock) user (`usermod -U`)
- ✅ Change password (`passwd`)

### Group Management
- ✅ Add group (`groupadd`)
- ✅ Modify group
  - Rename group (`groupmod -n`)
  - Add user to group (`usermod -aG`)
  - Remove user from group (`gpasswd -d`)
  - Show group info (`getent group`)
- ✅ Delete group (with safety check if used as a primary group)
- ✅ List groups
  - Normal groups only (GID ≥ 1000)
  - All groups (root only)

---

## Requirements

- Linux distribution with:
  - Python 3
  - `whiptail` installed
  - Standard user/group commands: `useradd`, `usermod`, `userdel`, `groupadd`, `groupmod`, `groupdel`, `gpasswd`, `getent`

### Install whiptail

**Debian/Ubuntu:**
```bash
sudo apt update
sudo apt install -y whiptail
