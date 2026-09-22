# SCP (Secure Copy)

`scp` (Secure Copy) is a command-line tool used to **securely transfer files and directories** between local and remote systems over SSH.

---

# Why Use SCP?

- Secure file transfers
- Uses SSH encryption
- Copy files between local and remote machines
- No separate FTP server required

---

# Basic Syntax

```bash
scp source destination
```

---

# Copy a Local File to a Remote System

```bash
scp localfile username@remote_host:/path/to/destination
```

Example:

```bash
scp notes.txt aryan@server.example.com:/home/aryan/
```

Copies `notes.txt` from the local machine to the remote server.

---

# Copy a Remote File to the Local Machine

```bash
scp username@remote_host:/path/to/file .
```

Example:

```bash
scp aryan@server.example.com:/home/aryan/report.pdf .
```

Copies `report.pdf` to the current local directory.

---

# Copy an Entire Directory

```bash
scp -r folder username@remote_host:/home/aryan/
```

- `-r` → Copy directories recursively.

---

# Common Options

| Option | Purpose |
|---------|---------|
| `-r` | Copy directories recursively |
| `-P port` | Connect using a custom SSH port |
| `-i key.pem` | Use a private SSH key |
| `-v` | Verbose output |

---

# Common Uses

- Upload files to a Linux server
- Download files from a remote machine
- Backup files securely
- Transfer directories over SSH

---

# Summary

- `scp` securely copies files using SSH.
- Copy local → remote or remote → local.
- Supports recursive directory copying with `-r`.
- Authentication works with passwords or SSH keys.
```