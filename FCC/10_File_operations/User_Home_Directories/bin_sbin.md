# The `/proc` Filesystem

The `/proc` directory is a **virtual (pseudo) filesystem** created by the Linux kernel. It does **not** contain real files stored on disk. Instead, it provides information about the kernel, hardware, running processes, and system configuration.

---

## Common Files in `/proc`

| File | Description |
|------|-------------|
| `/proc/cpuinfo` | Information about the CPU(s) installed in the system. |
| `/proc/interrupts` | Displays hardware interrupt information. |
| `/proc/meminfo` | Shows memory usage and RAM statistics. |
| `/proc/mounts` | Lists all currently mounted filesystems. |
| `/proc/partitions` | Displays disk partitions recognized by the kernel. |
| `/proc/version` | Shows the Linux kernel version and build information. |

---

## Purpose of Each File

### `/proc/cpuinfo`

Contains details such as:

- CPU model
- Number of cores
- Cache size
- CPU frequency
- Vendor information

Example:

```bash
cat /proc/cpuinfo
```

---

### `/proc/interrupts`

Shows which hardware interrupts are being used by devices such as:

- Keyboard
- Mouse
- Network cards
- Storage devices

Example:

```bash
cat /proc/interrupts
```

---

### `/proc/meminfo`

Displays memory statistics including:

- Total RAM
- Free RAM
- Cached memory
- Swap usage
- Available memory

Example:

```bash
cat /proc/meminfo
```

---

### `/proc/mounts`

Lists every filesystem currently mounted on the system.

Example:

```bash
cat /proc/mounts
```

---

### `/proc/partitions`

Shows all storage devices and their partitions recognized by the kernel.

Example:

```bash
cat /proc/partitions
```

---

### `/proc/version`

Displays the currently running Linux kernel version.

Example:

```bash
cat /proc/version
```

---

## Key Points

- `/proc` is **not stored on disk**.
- It is generated dynamically by the Linux kernel.
- Used to inspect **system hardware**, **kernel information**, **memory**, **CPU**, **partitions**, and **mounted filesystems**.
- Most files can be viewed using commands like `cat`, `less`, or `grep`.