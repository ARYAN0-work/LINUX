# Additional Linux Directories

Besides the common directories (`/bin`, `/etc`, `/home`, `/dev`, `/proc`, etc.), Linux also contains several other important directories.

---

# `/opt`

The `/opt` directory stores **optional third-party application software**.

It is commonly used when software is installed manually instead of through the system package manager.

### Examples

```text
/opt/google/chrome
/opt/intellij
/opt/vscode
```

---

# `/sys`

The `/sys` directory is a **virtual filesystem (sysfs)**.

It provides information about:

- Hardware devices
- Kernel objects
- Drivers
- System configuration

It can also be used to change certain kernel parameters while the system is running.

### Typical Uses

- Viewing hardware information
- Managing devices
- Kernel debugging
- Power management

---

# `/srv`

The `/srv` directory stores **data served by system services**.

For example:

- Web server files
- FTP server data
- File server resources

### Examples

```text
/srv/www
/srv/ftp
```

---

# `/tmp`

The `/tmp` directory stores **temporary files**.

Applications create temporary files here while running.

Characteristics:

- Usually cleared after reboot
- World-writable
- Used for temporary program data

### Examples

```text
/tmp/install.log
/tmp/cache.tmp
```

---

# `/usr`

The `/usr` directory contains **most user applications, libraries, documentation, and shared resources**.

It is one of the largest directories in Linux.

---

# Important `/usr` Subdirectories

| Directory | Purpose |
|-----------|---------|
| `/usr/bin` | Main executable commands available to users |
| `/usr/sbin` | Non-essential system administration commands |
| `/usr/lib` | Libraries used by `/usr/bin` and `/usr/sbin` |
| `/usr/lib64` | 64-bit libraries |
| `/usr/include` | Header files used for compiling C/C++ programs |
| `/usr/share` | Architecture-independent shared data (icons, docs, fonts, locales, man pages) |
| `/usr/src` | Source code (often Linux kernel source) |
| `/usr/local` | Locally installed software and custom programs |

---

## `/usr/local`

This directory is reserved for software installed manually by the system administrator.

It has its own structure:

```text
/usr/local/bin
/usr/local/lib
/usr/local/include
/usr/local/share
/usr/local/sbin
```

Programs installed here do not interfere with package-manager-installed software.

---

# Summary

| Directory | Purpose |
|-----------|---------|
| `/opt` | Optional third-party software |
| `/sys` | Virtual filesystem containing kernel and hardware information |
| `/srv` | Data served by services (web, FTP, etc.) |
| `/tmp` | Temporary files |
| `/usr` | User applications, libraries, documentation, and shared resources |

---

# Key Points

- `/opt` is used for optional applications.
- `/sys` exposes kernel and hardware information.
- `/srv` stores data served by network services.
- `/tmp` stores temporary files and is often cleared after reboot.
- `/usr` contains most user-space programs and supporting files.
- `/usr/local` is the preferred location for manually installed software.
```