# Terminating Processes

## What Does "Terminate" Mean?

Terminating a process means stopping its execution.

Linux uses **signals** to communicate with running processes. A signal can request a process to stop, pause, continue, or perform another action.

---

## The `kill` Command

The `kill` command sends a signal to a process.

Basic syntax:

```bash
kill <PID>
```

Example:

```bash
kill 2456
```

By default, this sends the **SIGTERM (15)** signal.

---

## SIGTERM (Signal 15)

SIGTERM politely asks a process to terminate.

```bash
kill -SIGTERM <PID>
```

or

```bash
kill -15 <PID>
```

Example:

```bash
kill -15 2456
```

### Characteristics

- Gracefully stops the process.
- Allows cleanup before exiting.
- Recommended whenever possible.

---

## SIGKILL (Signal 9)

If a process refuses to stop, forcefully terminate it using SIGKILL.

```bash
kill -SIGKILL <PID>
```

or

```bash
kill -9 <PID>
```

Example:

```bash
kill -9 2456
```

### Characteristics

- Immediately stops the process.
- Cannot be ignored or caught.
- No cleanup is performed.
- Use only when SIGTERM fails.

---

## SIGTERM vs SIGKILL

| Signal | Number | Behavior | Recommended |
|---------|--------|----------|-------------|
| SIGTERM | 15 | Gracefully terminates the process | ✅ Yes |
| SIGKILL | 9 | Immediately kills the process | ⚠️ Only if necessary |

---

## Common Workflow

1. Find the process ID:

```bash
ps
```

or

```bash
top
```

2. Try to terminate it gracefully:

```bash
kill <PID>
```

3. If it doesn't stop:

```bash
kill -9 <PID>
```

---

# Key Takeaways

- Use `kill` to send signals to processes.
- `kill` without options sends **SIGTERM (15)**.
- `kill -9` sends **SIGKILL (9)**.
- Prefer **SIGTERM** before using **SIGKILL**.
- SIGKILL should be the last resort.