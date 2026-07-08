# Types of Linux Processes

Linux processes can be categorized based on how they are created and how they run.

---

## 1. Interactive Processes

Processes started directly by a user through the terminal or a graphical interface (GUI).

### Characteristics

- Started manually
- User-controlled
- Runs in the foreground or background
- Ends when the user closes it or terminates it

### Examples

- `bash`
- `firefox`
- `top`
- `vim`

---

## 2. Batch Processes

Processes that are scheduled to run automatically without user interaction.

### Characteristics

- Executed automatically
- Often run in the background
- Used for repetitive or scheduled tasks

### Examples

- `updatedb`
- `ldconfig`

---

## 3. Daemons

Daemons are background services that run continuously and provide system or network services.

### Characteristics

- Start during system boot or when required
- Run continuously
- Usually have names ending with `d` (daemon)

### Examples

- `sshd` – SSH server
- `httpd` – Web server
- `libvirtd` – Virtualization service

---

## 4. Threads

Threads are lightweight execution units within a process.

A single process can have multiple threads that share the same memory and resources.

### Characteristics

- Share memory with the parent process
- Faster than creating new processes
- Allow concurrent execution

### Examples

- Firefox tabs
- GNOME Terminal
- Multithreaded applications

---

## 5. Kernel Threads

Kernel threads are created and managed by the Linux kernel.

Users do not directly start or stop them.

### Characteristics

- Run in kernel space
- Perform low-level system tasks
- Managed entirely by the kernel

### Examples

- `kthreadd`
- `migration`
- `ksoftirqd`

---

# Comparison

| Type | Started By | Runs In | Example |
|------|------------|---------|---------|
| Interactive | User | Foreground/Background | `bash`, `firefox` |
| Batch | Scheduler | Background | `updatedb` |
| Daemon | System | Background | `sshd`, `httpd` |
| Thread | Process | Inside a Process | Firefox thread |
| Kernel Thread | Linux Kernel | Kernel Space | `kthreadd` |

---

# Key Takeaways

- **Interactive processes** are started by users.
- **Batch processes** run automatically on a schedule.
- **Daemons** provide background services.
- **Threads** are lightweight execution units inside a process.
- **Kernel threads** perform operating system tasks and are managed by the Linux kernel.