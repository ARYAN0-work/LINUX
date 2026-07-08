# Disk Partitions in Linux

A **partition** is a logical division of a physical storage device (HDD or SSD). Each partition can have its own filesystem and can be used independently by the operating system.

Linux allows multiple partitions on the same disk, each serving a different purpose such as booting the system, storing user data, or hosting another operating system.

---

## Example Partition Layout

The screenshot shows a disk (`/dev/sda`) divided into multiple partitions.

| Partition | Purpose | Filesystem |
|-----------|---------|------------|
| `/dev/sda1` | EFI System Partition | FAT32 |
| `/dev/sda2` | Microsoft Reserved Partition | Unknown |
| `/dev/sda3` | Windows Partition | NTFS |
| `/dev/sda4` | Windows Recovery Partition | NTFS |
| `/dev/sda5` | Ubuntu Root Partition | ext4 |
| `/dev/sda6` | CentOS Root Partition | ext4 |
| `/dev/sda7` | EFI Partition | FAT16 |
| `/dev/sda8` | RHEL Root Partition | ext4 |

---

## Common Linux Filesystems Used on Partitions

- **ext4** – Most common Linux filesystem.
- **FAT32/FAT16** – EFI System Partitions.
- **NTFS** – Windows partitions.
- **Swap** *(not shown in the screenshot)* – Virtual memory used by Linux.

---

## Why Use Partitions?

- Install multiple operating systems (Dual Boot).
- Separate system files from user data.
- Improve organization.
- Easier backup and recovery.
- Different partitions can use different filesystems.

---

## GParted

The screenshot uses **GParted (GNOME Partition Editor)**.

GParted allows you to:

- View partitions.
- Create new partitions.
- Delete partitions.
- Resize partitions.
- Format partitions.
- Change partition labels.
- Manage mount points.

---

## Naming Convention

Linux storage devices are named like:

```text
/dev/sda
```

Where:

- `/dev` → Device directory.
- `sd` → SCSI/SATA storage device.
- `a` → First disk (`b` = second disk, `c` = third disk, ...).

Partitions are numbered:

```text
/dev/sda1
/dev/sda2
/dev/sda3
```

Example:

- `/dev/sda` → Entire disk.
- `/dev/sda1` → First partition.
- `/dev/sda2` → Second partition.
- `/dev/sda6` → Sixth partition.

---

## Key Points

- A single disk can contain **multiple partitions**.
- Each partition can have its **own filesystem**.
- Linux identifies disks under the `/dev` directory.
- Tools like **GParted** make partition management easy through a graphical interface.
- Different operating systems can coexist on the same disk using separate partitions.