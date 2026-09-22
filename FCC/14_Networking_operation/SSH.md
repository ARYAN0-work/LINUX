# SSH (Secure Shell)

SSH (Secure Shell) is a secure network protocol used to **connect to remote computers** over a network. It encrypts all communication between the client and the server.

---

# Why Use SSH?

- Secure remote login
- Execute commands on remote systems
- Transfer files securely (using SCP/SFTP)
- Manage Linux servers remotely
- Create encrypted tunnels (SSH Tunneling)

---

# How SSH Works

```text
SSH Client  ───── Encrypted SSH Tunnel ─────►  SSH Server
```

All communication is encrypted before being sent over the internet.

---

# Connect to a Remote System

### Using `-l`

```bash
ssh -l username hostname
```

Example:

```bash
ssh -l aryan server.example.com
```

---

### Using `username@host` (Most Common)

```bash
ssh username@hostname
```

Example:

```bash
ssh aryan@server.example.com
```

---

# Execute a Remote Command

Instead of opening an interactive shell, execute a command directly.

```bash
ssh username@hostname "command"
```

Example:

```bash
ssh aryan@server.example.com "ls -l"
```

---

# Common Options

| Option | Purpose |
|---------|---------|
| `-l user` | Specify username |
| `-p port` | Connect using a different port |
| `-i key.pem` | Use a private key for authentication |
| `-v` | Verbose mode for debugging |

---

# SSH Tunneling

SSH can securely forward network traffic through an encrypted tunnel.

Uses:

- Secure access to internal services
- Secure database connections
- Port forwarding
- Bypass insecure networks

---

# Common Uses

- Remote server administration
- Execute commands remotely
- Secure file transfers
- Secure networking through tunnels
- Remote development

---

# Summary

- SSH provides encrypted remote access.
- Connect using `ssh username@host`.
- Run remote commands directly from the terminal.
- Supports authentication with passwords or SSH keys.
- Widely used by Linux administrators and developers.