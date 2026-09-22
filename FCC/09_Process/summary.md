# Linux Processes - Summary

## What is a Process?

- A process is a **running instance of a program**.
- Every running application becomes a process.
- The Linux **kernel** manages all processes and allocates CPU, memory, and other resources.

---

## Types of Processes

- **Interactive** – Started by the user.
- **Batch** – Scheduled, non-interactive jobs.
- **Daemon** – Background services.
- **Thread** – Lightweight execution unit within a process.
- **Kernel Thread** – Created and managed by the kernel.

---

## Process States

- Running
- Sleeping
- Waiting
- Stopped
- Zombie

---

## Process Identifiers

- **PID** – Process ID.
- **PPID** – Parent Process ID.
- **TID** – Thread ID.

Every process has a unique PID.

---

## User and Group IDs

- **RUID** – Real User ID (owner of the process)
- **EUID** – Effective User ID (permissions currently used)
- **RGID** – Real Group ID
- **EGID** – Effective Group ID

These determine who owns the process and what permissions it has.

---

## Process Priority

Linux schedules processes using priorities.

- **Nice value:** `-20` (highest priority) to `19` (lowest priority)
- Lower nice value = Higher priority
- Higher nice value = Lower priority

Commands:

```bash
nice
renice
```

---

## Managing Processes

Stop a process gracefully:

```bash
kill PID
```

Force kill:

```bash
kill -9 PID
```

Common signals:

- SIGTERM (15)
- SIGKILL (9)

Always prefer **SIGTERM** before **SIGKILL**.

---

## Foreground & Background Jobs

Stop current process:

```bash
Ctrl + C
```

Suspend process:

```bash
Ctrl + Z
```

Resume in background:

```bash
bg
```

Bring to foreground:

```bash
fg
```

List jobs:

```bash
jobs
```

---

## Viewing Processes

Show processes:

```bash
ps
```

BSD style:

```bash
ps aux
```

UNIX style:

```bash
ps -ef
```

Tree view:

```bash
pstree
```

---

## Monitoring Processes

```bash
top
```

Useful keys inside `top`:

- `P` → Sort by CPU
- `M` → Sort by Memory
- `k` → Kill process
- `r` → Change priority (renice)
- `q` → Quit

---

## Scheduling Tasks

### at

Run a command once at a future time.

### cron

Run commands repeatedly using schedules.

Edit jobs:

```bash
crontab -e
```

List jobs:

```bash
crontab -l
```

Cron format:

```text
* * * * * command
│ │ │ │ │
│ │ │ │ └── Day of Week
│ │ │ └──── Month
│ │ └────── Day
│ └──────── Hour
└────────── Minute
```

---

## sleep Command

Pause execution.

Examples:

```bash
sleep 5
sleep 10m
sleep 2h
sleep 1d
```

Supports:

- `s` Seconds
- `m` Minutes
- `h` Hours
- `d` Days

---

# Commands Covered

```bash
ps
pstree
top
kill
nice
renice
jobs
bg
fg
sleep
crontab
at
```

---

# Key Takeaways

- A process is a running program.
- Every process has a unique PID.
- The Linux kernel schedules and manages processes.
- Priorities are controlled using nice values.
- `ps`, `pstree`, and `top` help inspect running processes.
- `kill` terminates processes using signals.
- `Ctrl+C`, `Ctrl+Z`, `bg`, and `fg` manage foreground/background jobs.
- `cron` automates recurring tasks.
- `sleep` pauses execution for a specified duration.