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

## Distributions

### **Debian**
- One of the oldest and most stable Linux distributions.
- Community-driven and known for reliability.
- Forms the base for many other Linux distributions.

### **Ubuntu**
- Based on Debian.
- Developed by Canonical.
- Beginner-friendly and widely used for desktops, servers, and cloud computing.
- One of the most popular Linux distributions.

### **Linux Mint**
- Based on Ubuntu (and indirectly Debian).
- Designed to be easy for users transitioning from Windows.
- Provides a polished desktop experience.

## Package Manager

| Distribution | Package Format | Package Manager |
|--------------|----------------|-----------------|
| Debian | `.deb` | `apt` |
| Ubuntu | `.deb` | `apt` |
| Linux Mint | `.deb` | `apt` |

## Key Facts

- Uses **DEB** (`.deb`) package format.
- Uses **APT (Advanced Package Tool)** as the package manager.
- Known for stability and reliability.
- Large software repositories with thousands of packages.
- One of the most popular Linux families.
- Ubuntu and Linux Mint are based on Debian.

## Relationship

```text
Linux Kernel
      │
      ▼
    Debian
      │
      ├── Ubuntu
      │      │
      │      └── Linux Mint
      │
      └── Other Debian-based distributions
```

## Additional Key Facts About the Debian Family

- **Debian** is the upstream distribution for Ubuntu. => "Upstream" means Debian is the original source where Ubuntu gets its raw materials (its code and software packages).
- Uses the **DPKG** package management system with **APT** as the front-end package manager.
- Widely used for servers, cloud deployments, and development environments.
- Ubuntu uses the **GNOME** desktop environment by default (since Ubuntu 17.10), but customizes it with its own look and feel.
- Linux Mint uses the **Cinnamon** desktop environment by default and is designed to provide a familiar desktop experience.