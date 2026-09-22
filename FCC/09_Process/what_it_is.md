# What is a Process?

## Definition

A **process** is a **running instance of a program**.

A program is a passive file stored on disk, while a process is the active execution of that program in memory.

---

## Program vs Process

| Program | Process |
|----------|----------|
| Stored on disk | Running in memory |
| Passive | Active |
| Executable file | Executing program |

Example:

```text
Program:
firefox

When executed:

Process:
Firefox running in memory
```

---

## How a Process Works

When you run a program:

1. The operating system loads the program into memory.
2. The Linux kernel creates a process.
3. The process requests system resources.
4. The kernel manages the process until it exits.

```text
Program
    │
    ▼
Linux Kernel
    │
    ▼
Running Process
```

---

## Process and the Linux Kernel

The Linux kernel is responsible for:

- Creating processes
- Scheduling CPU time
- Allocating memory
- Managing input/output (I/O)
- Providing access to hardware resources

```text
        Process 1
        Process 2
        Process 3
            │
            ▼
      Linux Kernel
      ├── CPU
      ├── Memory
      ├── Disk
      └── Devices
```

The kernel acts as the bridge between running programs and the computer's hardware.

---

## Why Do We Need Processes?

Processes allow multiple programs to run at the same time.

For example:

- Web browser
- VS Code
- Terminal
- Music player

Each runs as its own process while the kernel shares system resources among them.

---

## Examples

Running:

```bash
firefox
```

creates a Firefox process.

Running:

```bash
python app.py
```

creates a Python process.

Running:

```bash
code .
```

creates a VS Code process.

---

# Key Points

- A process is a running program.
- Programs become processes when executed.
- The Linux kernel manages all processes.
- Processes use CPU, memory, storage, and other system resources.
- Multiple processes can run simultaneously.