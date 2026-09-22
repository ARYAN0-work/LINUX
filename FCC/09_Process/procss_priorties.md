# Process Priorities

## What is Process Priority?

Every process has a priority that determines how much CPU time it receives.

The Linux scheduler uses this priority to decide which process should run first.

---

## Nice Value

Linux uses a **nice value** to influence a process's priority.

Range:

```text
-20 ------------------------ 19
Highest Priority      Lowest Priority
```

- **-20** → Highest priority (gets more CPU time)
- **0** → Default priority
- **19** → Lowest priority (gets less CPU time)

---

## Important Note

A **lower nice value means a higher priority**.

| Nice Value | Priority |
|------------|----------|
| -20 | Highest |
| 0 | Default |
| 19 | Lowest |

---

## Why is it Called "Nice"?

A process with a **higher nice value** is being "nice" to other processes because it gives them more CPU time.

Example:

```text
Nice = 19

"I'm being nice.
Other processes can use the CPU first."
```

---

# Viewing Process Priority

Display running processes:

```bash
ps -el
```

or

```bash
top
```

Both commands display the **NI (Nice)** value.

---

# Starting a Process with a Nice Value

```bash
nice -n 10 command
```

Example:

```bash
nice -n 10 python app.py
```

Starts the process with a nice value of **10**.

---

# Changing the Nice Value

Use:

```bash
renice
```

Syntax:

```bash
renice <nice_value> -p <PID>
```

Example:

```bash
renice 5 -p 2345
```

Changes process **2345** to a nice value of **5**.

---

# Real-Time Priority

Some critical system tasks use **real-time scheduling**.

Examples:

- Audio processing
- Video streaming
- Industrial control
- Robotics

These processes are scheduled differently from normal processes.

---

# Common Commands

```bash
ps -el
top
nice -n 10 command
renice 5 -p 1234
```

---

# Key Takeaways

- Linux schedules processes based on priority.
- Nice values range from **-20 to 19**.
- Lower nice value = Higher priority.
- Default nice value = **0**.
- Use `nice` to start a process with a custom priority.
- Use `renice` to change the priority of a running process.