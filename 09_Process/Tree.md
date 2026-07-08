# Process Tree

## What is a Process Tree?

A process tree shows the **parent-child relationship** between processes.

Every process (except the very first system process) is created by another process.

```text
Parent Process
      │
      ├── Child Process 1
      ├── Child Process 2
      └── Child Process 3
```

---

# Why Do We Need a Process Tree?

A process tree helps you:

- Understand how processes are related.
- Find parent and child processes.
- Debug applications.
- Monitor system activity.

---

# Viewing the Process Tree

## `pstree`

Display all running processes as a tree.

```bash
pstree
```

Example:

```text
systemd
├── NetworkManager
├── sshd
│   └── bash
│       └── vim
├── cron
└── firefox
    ├── firefox
    ├── firefox
    └── firefox
```

---

## Display Process IDs

Use:

```bash
pstree -p
```

Example:

```text
systemd(1)
├── sshd(742)
│   └── bash(1001)
│       └── vim(1250)
```

---

## Display User Ownership

```bash
pstree -u
```

Shows the user who owns each process.

---

## Display a Specific Process Tree

```bash
pstree <PID>
```

Example:

```bash
pstree 1001
```

Displays only that process and its children.

---

# Relationship with PPID

Each process has:

- **PID** → Process ID
- **PPID** → Parent Process ID

Example:

```text
systemd (PID 1)
        │
        ▼
bash (PID 1200)
PPID = 1
        │
        ▼
vim (PID 1500)
PPID = 1200
```

The process tree is built using these parent-child relationships.

---

# Common Commands

```bash
pstree
pstree -p
pstree -u
pstree <PID>
```

---

# Key Takeaways

- A process tree shows parent-child relationships.
- `pstree` displays processes in a hierarchical tree.
- `pstree -p` shows Process IDs (PIDs).
- `pstree -u` shows process owners.
- The tree is built using **PID** and **PPID** values.