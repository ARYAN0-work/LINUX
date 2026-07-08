# Debian Family

```text
Linux Kernel
      │
      ▼
    Debian
      │
      ├── Ubuntu
      │
      └── Linux Mint
```

# CONFUSION
- Debian is the main distribution.
- Ubuntu is built from Debian.
- Linux Mint is built from Ubuntu (so it's also indirectly based on Debian).



## Package Manager

| Distribution | Package Format | Package Manager |
|--------------|----------------|-----------------|
| Debian       | `.deb` | `apt` |
| Ubuntu       | `.deb` | `apt` |
| Linux Mint   | `.deb` | `apt` |

- .deb = APK file on Android
- apt = Play Store that installs and manages those APKs

## Key Facts

- Uses **DEB** (`.deb`) package format.
- Uses **APT (Advanced Package Tool)** as the package manager.
- Known for stability and reliability.
- Large software repositories with thousands of packages.
- One of the most popular Linux families.
- Ubuntu and Linux Mint are based on Debian.


## Additional Key Facts About the Debian Family

- **Debian** is the upstream distribution for Ubuntu. => "Upstream" means Debian is the original source where Ubuntu gets its raw materials (its code and software packages).

- Debian develops software first, and Ubuntu takes that work and builds its own operating system on top of it.

- Simple flow:
Debian → Ubuntu → Linux Mint

- DPKG vs APT
dpkg is the low-level package manager that installs .deb files.
apt is a higher-level tool that uses dpkg in the background and also downloads packages and handles dependencies.

You will mostly use apt. You rarely need to use dpkg directly.

- Desktop Environments

1. A desktop environment is simply the look and feel of Linux (windows, menus, taskbar, icons).

2. Ubuntu → GNOME
Linux Mint → Cinnamon

This only affects the graphical interface, not the Linux kernel or terminal.