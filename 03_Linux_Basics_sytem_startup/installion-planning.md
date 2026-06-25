# Linux Partitions

A **hard disk** can be divided into multiple sections called **partitions**.

Think of a hard disk as a large apartment building.

Each apartment has a different purpose.

```
Linux Hard Disk (sda)
│
├── sda1 → /
├── sda2 → /home
├── sda3 → /var
└── sda4 → swap
```

Each partition has its own filesystem.

---

## What does `sda` mean?

Linux names storage devices like this:

```
sda
```

- **sd** → Storage Device (SCSI/SATA/SSD)
- **a** → First hard disk

Examples:

```
sda  → First disk
sdb  → Second disk
sdc  → Third disk
```

---

## What does `sda1` mean?

```
sda1
```

means

> Partition 1 on the first disk.

Similarly,

```
sda2
```

means

> Partition 2 on the first disk.

---

## Common Partitions

### `/` (Root)

Contains:

- Linux operating system
- Kernel
- System files
- Applications

Usually mounted on:

```
sda1
```

---

### `/home`

Contains:

- User files
- Downloads
- Documents
- Pictures

Usually mounted on

```
sda2
```

Keeping `/home` on a separate partition allows reinstalling Linux without deleting personal files.

---

### `/var`

Stores data that changes frequently.

Examples:

- Logs
- Cache
- Databases
- Mail

Often placed on its own partition on servers because it grows over time.

---

### `swap`

Swap is **not a normal filesystem**.

It acts as extra memory when RAM becomes full.

Example:

```
RAM = 8 GB

RAM becomes full

↓

Linux temporarily stores inactive memory pages inside the swap partition.
```

Swap is much slower than RAM but helps prevent crashes when memory is exhausted.

---

# Why create multiple partitions?

Advantages:

- Better organization
- Easier backup
- Safer reinstalls
- Separate user data from system files
- Prevent logs (`/var`) from filling the system partition

---

# In Simple Words

Think of your hard disk as a building.

```
Building (Hard Disk)
        │
 ┌──────┼────────────┐
 │      │            │
Room 1  Room 2    Room 3    Room 4
  /     /home      /var     swap
```

Each room has a different purpose.

They all belong to the same building (the hard disk).

---

# Important

The picture is only an example.

Your Linux installation may have:

- one partition (`/`)
- two partitions (`/` and `/home`)
- many partitions

You can check your own partitions with:

```bash
lsblk
```

or

```bash
df -h
```

# Primary, Extended and Logical Partitions (MBR)

Older hard disks using the **MBR (Master Boot Record)** partition table had a limitation:

- Maximum **4 Primary Partitions**

```
Hard Disk
│
├── Primary
├── Primary
├── Primary
└── Primary
```

If you needed more than 4 partitions, one primary partition had to become an **Extended Partition**.

---

## Extended Partition

An **Extended Partition** is like a **container**.

It doesn't store files directly.

Instead, it holds **Logical Partitions**.

```
Hard Disk
│
├── Primary
├── Primary
├── Primary
└── Extended
      │
      ├── Logical
      ├── Logical
      ├── Logical
      └── ...
```

---

## Example

```
Hard Disk
│
├── Primary
│      └── Windows
│
├── Primary
│      └── Windows Recovery
│
├── Primary
│      └── Swap
│
└── Extended
       │
       ├── Linux /
       ├── /home
       └── /var
```

The Linux partitions are stored inside the Extended Partition as Logical Partitions.

---

## Why?

MBR only allowed **4 primary partitions**.

Extended partitions were invented to bypass this limitation.

---

## Modern Systems

Today, most computers use:

- GPT (GUID Partition Table)
- UEFI

GPT removes the 4-partition limit.

You can create many partitions without needing an Extended Partition.

---

## In Simple Words

Think of a bookshelf.

```
Shelf
│
├── Book
├── Book
├── Book
└── Box
      │
      ├── Book
      ├── Book
      └── Book
```

- Primary Partition = Book
- Extended Partition = Box
- Logical Partition = Books inside the box

The box exists only to hold more books.