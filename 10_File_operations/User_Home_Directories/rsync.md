# Using `rsync`

`rsync` (Remote Sync) is one of the most powerful Linux utilities for copying, synchronizing, and backing up files.

Unlike `cp`, `rsync` transfers **only the changed parts** of files, making it much faster for repeated backups.

---

# Why Use `rsync`?

- Fast incremental backups
- Synchronize local directories
- Synchronize remote servers
- Preserve file permissions and timestamps
- Compress data during transfer
- Resume interrupted transfers

---

# Basic Syntax

```bash
rsync [options] source destination
```

Example:

```bash
rsync -av Documents/ Backup/
```

### Common Options

| Option | Description |
|---------|-------------|
| `-a` | Archive mode (preserves permissions, timestamps, symbolic links, ownership, etc.) |
| `-v` | Verbose output |
| `-z` | Compress data during transfer |
| `-h` | Human-readable file sizes |
| `--delete` | Delete files in destination that no longer exist in source |

---

# Local Backup

```bash
rsync -av project/ backup/
```

Copies only modified files from `project/` to `backup/`.

---

# Remote Backup

```bash
rsync -av project/ user@host:/home/user/backups/
```

Remote destination format:

```text
username@hostname:/destination/path
```

Example:

```text
someone@host
```

---

# Compression Utilities

Linux commonly uses these compression tools along with backups.

| Command | Usage |
|---------|-------|
| `gzip` | Most commonly used Linux compression utility |
| `bzip2` | Produces smaller files than `gzip`, but is slower |
| `xz` | Provides the highest compression ratio (smallest files) |
| `zip` | Cross-platform archive format, commonly used with Windows |

---

# Summary

- `rsync` is the preferred backup and synchronization tool.
- It copies only changed files, saving time and bandwidth.
- Supports both local and remote backups.
- Preserves file metadata in archive mode (`-a`).
- Compression tools like `gzip`, `bzip2`, `xz`, and `zip` reduce storage space for backups.