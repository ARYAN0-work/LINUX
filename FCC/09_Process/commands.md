# Job Control

Linux allows you to control processes running in the terminal.

Job control lets you:

- Stop a process
- Resume a process
- Move it to the background
- Bring it back to the foreground

---

# Ctrl + C

Stops (terminates) the currently running process.

Example:

```bash
ping google.com
```

Press:

```text
Ctrl + C
```

Result:

- Sends **SIGINT (Signal 2)**
- The process exits.

---

# Ctrl + Z

Suspends (pauses) the current process.

Example:

```bash
sleep 100
```

Press:

```text
Ctrl + Z
```

Result:

- Sends **SIGTSTP**
- The process is paused.
- It does **not** terminate.

---

# jobs

Lists jobs running in the current shell.

```bash
jobs
```

Example output:

```text
[1]+  Stopped    sleep 100
```

---

# bg

Resumes a stopped job in the background.

Syntax:

```bash
bg
```

or

```bash
bg %1
```

Example:

```bash
sleep 100
Ctrl + Z
bg
```

The process continues running without occupying the terminal.

---

# fg

Brings a background job back to the foreground.

Syntax:

```bash
fg
```

or

```bash
fg %1
```

Example:

```bash
fg
```

The process becomes interactive again.

---

# Workflow Example

Start a process:

```bash
sleep 100
```

Pause it:

```text
Ctrl + Z
```

Check jobs:

```bash
jobs
```

Continue in background:

```bash
bg
```

Bring back:

```bash
fg
```

Terminate:

```text
Ctrl + C
```

---

# Summary

| Command | Action |
|---------|--------|
| `Ctrl + C` | Stop the process |
| `Ctrl + Z` | Pause the process |
| `jobs` | Show background/stopped jobs |
| `bg` | Resume a job in the background |
| `fg` | Bring a job to the foreground |

---

# Key Takeaways

- **Ctrl + C** → Terminates the process.
- **Ctrl + Z** → Suspends (pauses) the process.
- **jobs** → Lists jobs in the current shell.
- **bg** → Continues a paused job in the background.
- **fg** → Brings a background job back to the foreground.

