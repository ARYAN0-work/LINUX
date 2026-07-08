# Backing Up Data in Linux

A **backup** is a copy of important files or directories that can be restored if the original data is lost, corrupted, or accidentally deleted.

Linux provides several tools for creating backups. The most common are:

- `cp`
- `rsync`
- `tar`

---

# 1. Backup Using `cp`

The `cp` command can be used to create a simple backup by copying files or directories.

## Backup a File

```bash
cp report.txt report_backup.txt
```

---

## Backup a Directory

```bash
cp -r project project_backup
```

### Explanation

- `-r` → Copy directories recursively.

---

# 2. Backup Using `rsync` (Recommended)

`rsync` is a powerful backup and synchronization tool.

Advantages:

- Copies only changed files.
- Faster than copying everything.
- Preserves permissions, ownership, timestamps, and symbolic links.
- Supports local and remote backups.

---

## Basic Syntax

```bash
rsync [options] source destination
```

---

## Local Backup

```bash
rsync -av Documents/ Backup/
```

### Explanation

- `-a` → Archive mode (preserves permissions, timestamps, links, etc.)
- `-v` → Verbose output

---

## Remote Backup

```bash
rsync -av Documents/ user@host:/backup/
```

The destination format is:

```text
username@hostname:/path/to/destination
```

Example:

```bash
rsync -av project/ someone@host:/home/someone/backups/
```

---

# Remote Target Format

A remote destination generally follows this format:

```text
username@hostname:/destination/path
```

Example shown in the lecture:

```text
someone@host
```

---

# 3. Backup Using `tar`

The `tar` command creates a single archive containing multiple files and directories.

Example:

```bash
tar -cvf backup.tar Documents/
```

---

# Summary

| Command | Purpose |
|---------|---------|
| `cp` | Simple file or directory backup |
| `rsync` | Efficient local and remote backups |
| `tar` | Create archive files for backup |

---

# Key Points

- Always keep backups of important data.
- `cp` is suitable for small, simple backups.
- `rsync` is the preferred tool for regular backups because it copies only changed files.
- `rsync` supports both local and remote backups.
- Remote backup paths use the format `username@hostname:/path`.
- `tar` combines multiple files into a single archive for easier storage and transfer.