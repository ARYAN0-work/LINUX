# Chapter 10 Summary – Linux File Operations & Filesystem

## Linux Filesystem

- The Linux filesystem starts at the **root directory (`/`)**.
- Everything in Linux is organized under this single directory tree.
- Directories help organize system files, user files, applications, and devices.

---

## Filesystem Hierarchy Standard (FHS)

- Linux distributions follow the **Filesystem Hierarchy Standard (FHS)**.
- FHS defines a common directory structure so software works consistently across distributions.

---

## Partitions

- A hard drive can contain multiple **partitions**.
- Each partition may contain its own filesystem.
- Partitions help separate operating system files, user data, backups, etc.

---

## Mounting

- A filesystem becomes accessible only after being **mounted**.
- A partition can be mounted on **any directory** (mount point).
- Common mount points include:
  - `/`
  - `/home`
  - `/mnt`
  - `/media`

---

## Network File System (NFS)

- **NFS (Network File System)** allows files and directories to be shared across computers on a network.
- Remote files can appear as if they are stored locally.

---

## Pseudo Filesystems

Directories like:

- `/proc`
- `/sys`

are **pseudo filesystems**.

They don't store real files on disk.

Instead, they expose:

- Kernel information
- Hardware information
- Running process information
- System configuration

---

## Important Directories

### `/home`

Stores user home directories.

Example:

```text
/home/alice
/home/bob
```

---

### `/bin`

Contains essential user commands.

Examples:

- `ls`
- `cp`
- `mv`
- `cat`

---

### `/sbin`

Contains system administration commands.

Examples:

- `mount`
- `reboot`
- `shutdown`

---

### `/proc`

Virtual filesystem containing process and kernel information.

Useful files:

```text
/proc/cpuinfo
/proc/meminfo
/proc/mounts
/proc/version
```

---

### `/dev`

Contains device files.

Examples:

```text
/dev/sda1
/dev/random
/dev/lp1
```

---

### `/var`

Stores frequently changing data.

Examples:

- Logs (`/var/log`)
- Print queues (`/var/spool`)
- Temporary files (`/var/tmp`)
- Package databases (`/var/lib`)

> `/var` may be placed on its own filesystem because it changes frequently.

---

### `/boot`

Contains files required to boot Linux.

Examples:

- Kernel (`vmlinuz`)
- initramfs
- System.map
- GRUB configuration

---

### `/lib` and `/lib64`

Contain shared libraries used by executables.

Example:

```text
/lib/libncurses.so.5.9
```

---

### `/media`

Automatically mounts removable storage.

Example:

```text
/meda/USB
```

---

### `/run/media`

Many modern Linux distributions mount removable drives here.

Example:

```text
/run/media/student/myusbdrive
```

---

### `/mnt`

Temporary mount point used by administrators.

---

### Other Important Directories

| Directory | Purpose |
|-----------|---------|
| `/opt` | Optional third-party software |
| `/sys` | Hardware and kernel information |
| `/srv` | Data served by services |
| `/tmp` | Temporary files |
| `/usr` | User applications and utilities |

Important `/usr` directories:

| Directory | Purpose |
|-----------|---------|
| `/usr/bin` | User programs |
| `/usr/sbin` | System administration programs |
| `/usr/lib` | Libraries |
| `/usr/lib64` | 64-bit libraries |
| `/usr/include` | Header files |
| `/usr/share` | Shared application data |
| `/usr/src` | Source code |
| `/usr/local` | Locally installed software |

---

# File Extensions

Linux **does not rely on file extensions** to determine file type.

Instead it uses:

- File headers (magic numbers)
- File metadata
- Permissions

Extensions are mainly for human readability.

---

# Copying Files

Basic copy command:

```bash
cp source destination
```

Useful for local file copies.

---

# `diff`

Compares two files or directories.

Useful options:

| Option | Description |
|--------|-------------|
| `-c` | Context output |
| `-r` | Recursive comparison |
| `-i` | Ignore case |
| `-w` | Ignore whitespace |
| `-q` | Report only if files differ |

---

# Creating Patch Files

Generate a patch:

```bash
diff -Nur originalfile newfile > patchfile
```

Apply a patch:

```bash
patch -p1 < patchfile
```

or

```bash
patch originalfile patchfile
```

Patch files are commonly used in open-source development to distribute code changes.

---

# Backups

Linux backups can be created using:

- `cp`
- `rsync`

`rsync` is preferred because it transfers **only changed files**, making backups much faster.

Example:

```bash
rsync -av source/ destination/
```

Remote backup example:

```bash
rsync -av project/ user@host:/backup/
```

---

# Compression Utilities

| Command | Usage |
|---------|-------|
| `gzip` | Standard Linux compression |
| `bzip2` | Better compression than gzip |
| `xz` | Highest compression ratio |
| `zip` | Cross-platform archive format |

---

# Key Takeaways

- Linux has a **single directory tree** rooted at `/`.
- FHS standardizes directory organization.
- Partitions become usable after being **mounted**.
- `/proc` and `/sys` are **virtual (pseudo) filesystems**.
- `/var` stores changing data like logs and caches.
- `/boot` contains files required to start Linux.
- Linux identifies files by **content**, not just extensions.
- `cp` copies files; `diff` compares them.
- Patch files distribute source code changes.
- `rsync` is the preferred tool for efficient backups and synchronization.
- `gzip`, `bzip2`, `xz`, and `zip` are common compression utilities.