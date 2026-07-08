# Process IDs

Every process and thread in Linux has an identifier.

These IDs help the operating system manage running tasks.

---

## Process ID (PID)

A **PID (Process ID)** uniquely identifies a running process.

Each process has its own PID.

Example:

```text
PID = 2543
```

---

## Parent Process ID (PPID)

Every process is usually created by another process.

The creator is called the **parent process**.

Its identifier is called the **PPID**.

```text
Parent Process
        │
        ▼
 Child Process
```

If the parent exits, Linux reassigns the child to another system process.

---

## Thread ID (TID)

A thread also has its own identifier called a **TID**.

### Single-threaded Process

```text
PID = TID
```

### Multi-threaded Process

```text
Process (PID 1200)
├── Thread (TID 1201)
├── Thread (TID 1202)
└── Thread (TID 1203)
```

All threads belong to the same process but have different Thread IDs.

---

## Comparison

| ID | Purpose |
|----|---------|
| PID | Identifies a process |
| PPID | Identifies the parent process |
| TID | Identifies an individual thread |

---

## Key Takeaways

- Every process has a unique **PID**.
- Every process usually has a **parent process (PPID)**.
- Every thread has its own **TID**.
- Multiple threads can belong to the same process.