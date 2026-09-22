# sleep Command

## What is `sleep`?

The `sleep` command pauses the execution of a program or script for a specified amount of time.

It is commonly used in:

- Shell scripts
- Automation
- Testing
- Delaying commands

---

## Basic Syntax

```bash
sleep NUMBER[SUFFIX]
```

Where `NUMBER` is the duration and `SUFFIX` specifies the unit.

---

## Time Suffixes

| Suffix | Meaning |
|---------|---------|
| s | Seconds (default) |
| m | Minutes |
| h | Hours |
| d | Days |

---

## Examples

Sleep for 5 seconds

```bash
sleep 5
```

Sleep for 10 minutes

```bash
sleep 10m
```

Sleep for 2 hours

```bash
sleep 2h
```

Sleep for 1 day

```bash
sleep 1d
```

---

## Common Usage

Wait before executing another command:

```bash
echo "Starting..."
sleep 3
echo "Done!"
```

Inside a loop:

```bash
while true
do
    echo "Checking..."
    sleep 5
done
```

---

## Why Use sleep?

- Delay script execution
- Reduce CPU usage in loops
- Wait for another process to finish
- Schedule repeated tasks with pauses

---

## Key Takeaways

- `sleep` pauses execution.
- Default unit is **seconds**.
- Supports `s`, `m`, `h`, and `d`.
- Frequently used in shell scripting and automation.