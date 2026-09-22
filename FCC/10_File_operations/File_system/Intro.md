# Linux Filesystem

The Linux filesystem is organized as a **hierarchical tree structure**.

At the very top is the **root directory (`/`)**, and every file and directory in the system branches from it.

```text
                 root (/)
                     │
     ┌───────────────┼───────────────┐
     │               │               │
   User-1       System Files      Devices
     │               │               │
 Data Files      Compilers        Devices
 Source Codes      Scripts      Sound Cards
                                Graphics Cards
```

---

## Filesystem Hierarchy

The root directory (`/`) contains many important directories, each serving a specific purpose.

| Directory | Purpose |
|-----------|---------|
| `/bin` | User binaries (essential commands) |
| `/sbin` | System binaries (administrative commands) |
| `/etc` | System configuration files |
| `/dev` | Device files |
| `/proc` | Process and kernel information |
| `/var` | Variable data (logs, cache, mail, etc.) |
| `/tmp` | Temporary files |
| `/usr` | User programs and applications |
| `/home` | Home directories for users |
| `/boot` | Boot loader files and kernel |
| `/lib` | Shared system libraries |
| `/opt` | Optional third-party applications |
| `/mnt` | Temporary mount directory |
| `/media` | Removable media (USB drives, CDs, etc.) |
| `/srv` | Service data |

---

## Important Notes

- The root directory is represented by `/`.
- Every file and directory begins from the root.
- Directory names are separated using **forward slashes (`/`)**.
- Linux organizes everything—including devices—as files within this hierarchy.