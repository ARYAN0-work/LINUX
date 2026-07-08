# Chapter 7: Command Line Operations - Summary

## Terminal & Console

- Virtual Terminals (VTs) are text-based consoles that use the keyboard and monitor directly.
- A terminal emulator provides terminal access inside a graphical desktop (GUI).
- You can log in locally through a terminal or remotely using SSH.
- Nothing is displayed while typing your password in the terminal (this is normal).

---

## System Control

- Shut down the system:

```bash
shutdown
```

- Reboot the system:

```bash
reboot
```

---

## File Paths

### Absolute Path

- Starts from the root directory (`/`).
- Always points to the same location.

Example:

```bash
/home/aryan/Documents/file.txt
```

### Relative Path

- Starts from the current working directory.

Example:

```bash
Documents/file.txt
```

---

## Links

- **Hard Link**
  - Points directly to the file's inode.
  - Remains valid even if the original filename is deleted.

- **Symbolic (Soft) Link**
  - Acts like a shortcut.
  - Breaks if the original file is removed.

---

## `cd` Command

```bash
cd -
```

Returns to the previous working directory.

---

## Finding Files

### `locate`

- Searches using a pre-built database.
- Very fast.
- Database may not always be up to date.

### `find`

- Searches the actual filesystem recursively.
- Slower than `locate`.
- Supports searching by:
  - Name
  - Type
  - Size
  - Time
  - Permissions
  - Running commands (`-exec`)

---

## Package Managers

### Debian / Ubuntu

- High-level:

```bash
apt
```

- Low-level:

```bash
dpkg
```

---

### Red Hat / Fedora

- High-level:

```bash
dnf
```

(Older systems use `yum`.)

- Low-level:

```bash
rpm
```

---

### SUSE

- High-level:

```bash
zypper
```

- Low-level:

```bash
rpm
```

---

## Common Package Manager Commands

Update packages:

```bash
sudo apt update
sudo dnf update
sudo zypper update
```

Install a package:

```bash
sudo apt install package
sudo dnf install package
sudo zypper install package
```

Remove a package:

```bash
sudo apt remove package
sudo dnf remove package
sudo zypper remove package
```

Search for a package:

```bash
apt search package
dnf search package
zypper search package
```

---

## Key Takeaways

- VTs are text consoles; terminal emulators run inside the GUI.
- Passwords are hidden while typing.
- Use `shutdown` and `reboot` for system control.
- Know the difference between absolute and relative paths.
- Hard links point to the inode; symbolic links point to the filename.
- `cd -` switches to the previous directory.
- `locate` is fast (database-based); `find` is flexible (filesystem-based).
- Ubuntu/Debian use `apt`, Fedora/RHEL use `dnf`, and SUSE uses `zypper`.
- High-level package managers handle dependency resolution, while low-level managers (`dpkg`, `rpm`) work directly with package files.