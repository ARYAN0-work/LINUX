# Process Scheduling

## What is Process Scheduling?

Linux can run many processes at the same time.

Since the CPU can execute only a limited number of instructions at any instant, the Linux **scheduler** decides which process gets CPU time.

---

## Run Queue

Processes waiting for CPU execution are placed in the **Run Queue**.

```text
Process 1
Process 2
Process 3
Process 4
Process 5
      │
      ▼
  Scheduler
      │
      ▼
      CPU
```

The scheduler continuously selects the next process from the run queue.

---

## What Does the Scheduler Do?

The scheduler decides:

- Which process runs next
- How long it runs
- When to switch to another process
- Which process has higher priority

---

## Scheduling Goals

The Linux scheduler tries to:

- Keep the CPU busy
- Share CPU time fairly
- Give interactive programs quick responses
- Maximize system performance

---

## Time Slice

Each process receives a small amount of CPU time called a **time slice** (or time quantum).

When the time slice expires:

1. The process pauses.
2. Another process gets CPU time.
3. The paused process returns to the run queue if it still has work.

---

## Key Takeaways

- Multiple processes compete for CPU time.
- The scheduler determines execution order.
- Waiting processes stay in the run queue.
- The scheduler helps the system remain responsive.