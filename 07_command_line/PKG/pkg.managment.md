# Working with Different Package Management Systems

Different Linux distributions use different package management systems. Although their commands differ, they all perform the same basic tasks:

- Install software
- Update software
- Remove software
- Search for packages
- Manage dependencies

---

# Package Manager Levels

Linux package management has two levels:

## 1. High-Level Package Manager

Provides an easy interface for users.

Features:
- Automatically resolves dependencies.
- Downloads packages from repositories.
- Installs, updates, and removes packages.

Examples:

| Distribution Family | High-Level Package Manager |
|---------------------|----------------------------|
| Debian / Ubuntu | `apt`, `apt-get` |
| Red Hat / CentOS | `yum`, `dnf` |
| SUSE | `zypper` |

---

## 2. Low-Level Package Manager

Works directly with package files.

Used by high-level package managers internally.

Examples:

| Distribution Family | Low-Level Package Manager |
|---------------------|---------------------------|
| Debian / Ubuntu | `dpkg` |
| Red Hat / CentOS | `rpm` |

---

# Package Manager Families

## Debian Family

Examples:

- Ubuntu
- Debian
- Linux Mint
- Pop!_OS

High-level:

```bash
apt
apt-get
```

Low-level:

```bash
dpkg
```

---

## Red Hat Family

Examples:

- RHEL
- CentOS
- Fedora
- Rocky Linux
- AlmaLinux

High-level:

```bash
yum
dnf
```

Low-level:

```bash
rpm
```

---

## SUSE Family

Examples:

- openSUSE
- SUSE Linux Enterprise

High-level:

```bash
zypper
```

Low-level:

```bash
rpm
```

---

# Relationship

```
High-Level Package Manager
        │
        ▼
Low-Level Package Manager
        │
        ▼
Linux System
```

Examples:

```
apt / apt-get
      │
      ▼
    dpkg
      │
      ▼
 Linux System
```

```
yum / dnf
     │
     ▼
    rpm
     │
     ▼
 Linux System
```

```
zypper
   │
   ▼
  rpm
   │
   ▼
Linux System
```

---

# Summary

- High-level package managers are used for everyday package management.
- Low-level package managers work directly with package files.
- Debian-based systems use `apt`/`apt-get` with `dpkg`.
- Red Hat-based systems use `yum` or `dnf` with `rpm`.
- SUSE systems use `zypper` with `rpm`.

---

# Interview Tip

For software engineering interviews, it's enough to know:

- Ubuntu/Debian → `apt` (`dpkg`)
- Red Hat/Fedora → `yum`/`dnf` (`rpm`)
- High-level managers handle dependencies automatically.
- Low-level managers work directly with package files.