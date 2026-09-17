# Linux Package Manager Commands

Package managers are used to install, update, remove, and search for software packages.

---

# Debian / Ubuntu

Package Manager:

```bash
apt
```

## Update package list

```bash
sudo apt update
```

Downloads the latest list of available packages.

---

## Upgrade installed packages

```bash
sudo apt upgrade
```

Upgrades installed software to the latest versions.

---

## Install a package

```bash
sudo apt install package_name
```

Example:

```bash
sudo apt install git
```

---

## Remove a package

```bash
sudo apt remove package_name
```

Example:

```bash
sudo apt remove git
```

---

## Search for a package

```bash
apt search package_name
```

Example:

```bash
apt search nginx
```

---

## Show package information

```bash
apt show package_name
```

Example:

```bash
apt show git
```

---

# Red Hat / Fedora

Package Manager:

```bash
dnf
```

> Older Red Hat systems use `yum`.

---

## Update packages

```bash
sudo dnf update
```

---

## Install a package

```bash
sudo dnf install package_name
```

---

## Remove a package

```bash
sudo dnf remove package_name
```

---

## Search for a package

```bash
dnf search package_name
```

---

## Show package information

```bash
dnf info package_name
```

---

# SUSE

Package Manager:

```bash
zypper
```

---

## Update packages

```bash
sudo zypper update
```

---

## Install a package

```bash
sudo zypper install package_name
```

---

## Remove a package

```bash
sudo zypper remove package_name
```

---

## Search for a package

```bash
zypper search package_name
```

---

# Common Operations

| Operation | Ubuntu/Debian | Fedora/RHEL | SUSE |
|-----------|---------------|-------------|------|
| Update package list | `apt update` | `dnf update` | `zypper update` |
| Install | `apt install` | `dnf install` | `zypper install` |
| Remove | `apt remove` | `dnf remove` | `zypper remove` |
| Search | `apt search` | `dnf search` | `zypper search` |

---

# Interview Tip

For software engineering interviews, remember:

- Ubuntu/Debian → `apt`
- Fedora/RHEL → `dnf` (`yum` on older systems)
- SUSE → `zypper`

The commands are almost identical—the package manager name changes, but the workflow (install, update, remove, search) stays the same.

## isme 20 min bus prompt pe commands likhlikhe sikhaya give time to this things bhut sarri commands and loading thi