## Linux Storage & Installation Summary

### 1. Partition

A **partition** is a **logical section of a physical disk**.

One hard disk can be divided into multiple partitions.

Example:

```text
Physical Disk (/dev/sda)

├── /dev/sda1
├── /dev/sda2
├── /dev/sda3
└── /dev/sda4
```

Each partition behaves like a separate storage area.

---

### 2. Filesystem

A **filesystem** is the way an operating system organizes and stores files on a partition.

Without a filesystem, a partition cannot store files.

Common filesystems:

* ext4 (Linux)
* NTFS (Windows)
* FAT32
* exFAT

Example:

```text
Partition
    ↓
Format
    ↓
ext4
    ↓
Ready to store files
```

---

### 3. Separating Data

Linux often separates data into different partitions.

Example:

```text
/        → Operating System
/home    → User files
/var     → Logs & databases
swap     → Virtual memory
```

Benefits:

* Easier backups
* Better security
* Easier maintenance
* Prevents one folder from filling the entire disk

---

### 4. Linux Boot Process

```text
Power On
    ↓
BIOS / UEFI
    ↓
MBR / GPT
    ↓
GRUB (Boot Loader)
    ↓
Linux Kernel
    ↓
initramfs
    ↓
systemd (/sbin/init)
    ↓
Login Screen / Terminal
```

Each component has a specific responsibility during system startup.

---

### 5. Choosing the Right Linux Distribution

Different Linux distributions are designed for different purposes.

#### Server

* Ubuntu Server
* Debian
* RHEL
* CentOS

#### Desktop

* Ubuntu
* Linux Mint
* Fedora
* openSUSE

#### Embedded Systems

* Yocto
* OpenEmbedded
* Android

Choose the distribution based on your requirements.

---

Once I understand Linux fundamentals on Ubuntu, switching to another distribution is mostly about learning a different package manager (apt, dnf, zypper, etc.), while the core Linux concepts remain the same.
