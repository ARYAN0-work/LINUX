# Shutdown, Reboot, Halt & Poweroff

These commands are used to shut down or restart a Linux system safely.

---

## Commands

| Command | Purpose | Example |
|---------|---------|---------|
| `shutdown -h` | Shut down (power off) the system | `sudo shutdown -h now` |
| `shutdown -r` | Reboot the system | `sudo shutdown -r now` |
| `halt` | Stop the system immediately | `sudo halt` |
| `poweroff` | Power off the machine | `sudo poweroff` |

---

## Schedule a Shutdown

Shutdown the system at a specific time:

```bash
sudo shutdown -h 10:00
```

With a message:

```bash
sudo shutdown -h 10:00 "Shutting down for scheduled maintenance"
```

Cancel the scheduled shutdown:

```bash
sudo shutdown -c
```

---

## Which Command Should I Use?

### Learn Well ✅

- `shutdown -h`
- `shutdown -r`

These are the recommended commands and are used on modern Linux systems.

---

### Just Know the Concept 📖

- `halt`
- `poweroff`

Older or less commonly used commands. They perform similar tasks but `shutdown` is generally preferred.

---

## Key Takeaway

- `shutdown -h` → Safely shut down the system.
- `shutdown -r` → Safely reboot the system.
- `shutdown -c` → Cancel a scheduled shutdown.
- `halt` and `poweroff` → Similar shutdown commands; know them but prefer `shutdown`.

> **For Backend & DevOps:**  
> You'll mostly use `shutdown` commands when managing Linux servers. Knowing `halt` and `poweroff` is useful, but they are not used as often.