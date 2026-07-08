# Linux Filesystem Types

A **filesystem** determines how data is stored, organized, and retrieved on a storage device. Linux supports many different filesystem types, each designed for specific use cases.

---

## Common Linux Filesystem Types

| Filesystem | Description |
|------------|-------------|
| **ext2** | Second Extended Filesystem; older Linux filesystem without journaling. |
| **ext3** | Added journaling support to ext2, improving reliability after crashes. |
| **ext4** | Default filesystem for many Linux distributions; fast, stable, and supports large files and partitions. |
| **XFS** | High-performance journaling filesystem designed for large files and enterprise workloads. |
| **Btrfs (B-tree File System)** | Modern filesystem supporting snapshots, checksums, compression, and advanced storage features. |
| **JFS (Journaled File System)** | IBM's journaling filesystem with good performance and low CPU usage. |
| **ReiserFS** | Older journaling filesystem known for efficient handling of many small files. |
| **Reiser4** | Successor to ReiserFS with additional features (rarely used today). |
| **SquashFS** | Compressed, read-only filesystem commonly used in Live CDs and embedded systems. |
| **Bcachefs** | Modern copy-on-write filesystem with compression, encryption, snapshots, and caching capabilities. |
| **exFAT / ext** | Other supported filesystem formats for compatibility and specialized use cases. |

---

## Most Common Filesystems Today

- **ext4** – Default choice for most Linux installations.
- **XFS** – Popular on enterprise servers.
- **Btrfs** – Used when advanced features like snapshots are required.
- **SquashFS** – Used for live systems and compressed read-only images.

---

## Key Points

- Linux supports **multiple filesystem types**.
- Different filesystems are optimized for **performance**, **reliability**, or **special features**.
- Most desktop Linux distributions use **ext4** by default.
- Server environments may use **XFS** or **Btrfs** depending on their requirements.