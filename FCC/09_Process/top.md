# Top Command

## What is `top`?

The `top` command displays **real-time information** about running processes and system resources.

Unlike `ps`, which shows a snapshot, `top` continuously updates the display.

---

# Basic Syntax

```bash
top
```

---

# What Does `top` Show?

The top section displays overall system information:

- System uptime
- Number of users
- Load average
- Running processes
- CPU usage
- Memory usage
- Swap usage

The bottom section lists all running processes.

---

# Common Columns

| Column | Meaning |
|---------|---------|
| PID | Process ID |
| USER | Process owner |
| PR | Priority |
| NI | Nice value |
| VIRT | Virtual memory |
| RES | Physical memory (RAM) |
| SHR | Shared memory |
| S | Process state |
| %CPU | CPU usage |
| %MEM | Memory usage |
| TIME+ | Total CPU time used |
| COMMAND | Process name |

---

# Useful Interactive Keys

| Key | Action |
|-----|--------|
| `P` | Sort by CPU usage |
| `M` | Sort by memory usage |
| `k` | Kill a process |
| `r` | Change process priority (renice) |
| `h` | Show help |
| `q` | Quit |

---

# Example

Start the monitor:

```bash
top
```

Quit:

```text
q
```

Kill a process:

```text
k
```

Then enter:

```text
PID
```

---

# top vs ps

| `ps` | `top` |
|-------|--------|
| Snapshot | Live monitoring |
| Runs once | Continuously updates |
| Good for scripting | Good for monitoring |

---

# Common Commands

```bash
top
```

---

# Key Takeaways

- `top` provides a live view of the system.
- Displays CPU, memory, load average, and running processes.
- Supports interactive commands.
- Useful for identifying resource-intensive processes.

## Additional Interactive Commands

While `top` is running, you can press the following keys:

| Key | Action |
|-----|--------|
| `t` | Show/Hide CPU summary information |
| `m` | Show/Hide memory information |
| `A` | Sort processes by top resource consumers |
| `r` | Change (renice) the priority of a process |
| `k` | Kill a process |
| `f` | Choose which columns to display |
| `o` | Change the order of displayed columns |
| `h` | Display help |
| `q` | Quit `top` |

---

## Example Workflow

Start `top`:

```bash
top
```

Inside `top`:

```text
P   → Sort by CPU usage
M   → Sort by memory usage
t   → Toggle CPU summary
m   → Toggle memory summary
A   → Sort by top resource consumers
r   → Change process priority
k   → Kill a process
f   → Select displayed fields
o   → Reorder displayed fields
q   → Quit
```

---

## Most Useful Shortcuts

| Key | Why You'll Use It |
|------|-------------------|
| `P` | Find processes using the most CPU |
| `M` | Find processes using the most memory |
| `k` | Kill a misbehaving process |
| `r` | Change a process priority |
| `q` | Exit `top` |