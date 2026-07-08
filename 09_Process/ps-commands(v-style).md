# PS Command

## What is `ps`?

The `ps` (Process Status) command displays information about currently running processes.

It is one of the most commonly used Linux process management commands.

---

# Basic Syntax

```bash
ps [options]
```

---

# Default Usage

```bash
ps
```

Displays processes running in the current terminal.

Example output:

```text
PID TTY          TIME CMD
2451 pts/0    00:00:00 bash
2540 pts/0    00:00:00 ps
```

---

# UNIX Style Options

These options begin with a **hyphen (-)**.

## `ps -e`

Display every process.

```bash
ps -e
```

---

## `ps -f`

Display full process information.

```bash
ps -f
```

Shows:

- UID
- PID
- PPID
- Start Time
- Command

---

## `ps -l`

Long format.

```bash
ps -l
```

Displays additional information such as:

- Priority
- Nice value
- State

---

## `ps -ef`

Display all processes in full format.

```bash
ps -ef
```

One of the most commonly used commands.

---

## `ps -el`

Display all processes in long format.

```bash
ps -el
```

Useful for viewing:

- Priority
- Nice value
- State

---

# BSD Style Options

BSD options **do not use a hyphen (-)**.

## `ps aux`

Shows nearly every running process.

```bash
ps aux
```

Displays:

- User
- PID
- CPU usage
- Memory usage
- Start time
- Command

Very commonly used by Linux administrators.

---

## `ps ax`

Display all processes.

```bash
ps ax
```

---

## `ps u`

User-oriented output.

```bash
ps u
```

---

# Display a Specific Process

Using a PID:

```bash
ps -p 1234
```

Example:

```bash
ps -p 2451
```

---

# Search for a Process

Using `grep`:

```bash
ps -ef | grep firefox
```

Example:

```bash
ps -ef | grep node
```

---

# Important Columns

| Column | Meaning |
|---------|---------|
| PID | Process ID |
| PPID | Parent Process ID |
| UID | User ID |
| CMD | Command |
| TTY | Terminal |
| STAT | Process State |
| NI | Nice Value |
| PRI | Priority |

---

# Common Commands

```bash
ps
ps -e
ps -f
ps -l
ps -ef
ps -el
ps aux
ps ax
ps -p 1234
ps -ef | grep nginx
```

---

# Key Takeaways

- `ps` displays running processes.
- `ps -ef` is commonly used to view all processes.
- `ps aux` is the BSD-style equivalent and is widely used.
- `ps -el` displays priority and nice values.
- Combine `ps` with `grep` to find specific processes.
