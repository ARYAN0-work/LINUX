/                    ← ROOT DIRECTORY (top of filesystem)
│
├── home/            ← directory for normal users
│   └── aryan/       ← YOUR home directory
│
├── root/            ← HOME DIRECTORY of the root USER
│
├── etc/
├── usr/
├── var/
├── dev/
└── ...

````bash
🔥 The confusing part

/ ≠ /root

/ = root directory → entire Linux filesystem
/root = root user's home directory
/home/aryan = your home directory

````

> cd /root -> pwd
>cd /home/aryan -> pwd

Why?

Because /root belongs to the root user, and your current user aryan does not have permission to enter it.

/
├── home/
│   └── aryan/    ← 🏠 your home
│
└── root/         ← 🔒 root user's home

> ls /boot

````bash
Normal Linux
     ↓
/boot
     ↓
Files needed for Linux boot
     ↓
kernel + initramfs + bootloader-related files

````

> ls /tmp | head

/tmp = temporary files

/tmp is a place where programs and the system can store temporary data while they're running

## BIOS :-

- The **BIOS (Basic Input/Output System)** is the first software that runs when a computer is powered on. Responsible for initializing the hardware before handing control over to the operating system.


## Power-On Self-Test (POST)

During POST, the BIOS checks whether essential hardware is functioning correctly.

Examples:

- CPU
- RAM
- Keyboard
- Display
- Storage devices

If a problem is found, the BIOS may display an error message or emit beep codes.

## Master Boot Record (MBR) and Boot Loader

After the BIOS finishes checking the hardware, it looks for the **Master Boot Record (MBR)** on the selected bootable storage device.

The **MBR** is the **first sector of a hard disk**. It contains:

- Boot loader code.
- The partition table.
- Information about which partition is bootable.


### Boot Sequence

```text
Power On
    │
    ▼
BIOS
    │
    ▼
Master Boot Record (MBR)
    │
    ▼
Boot Loader (GRUB)
    │
    ▼
Linux Kernel
```

### MBR Structure


```text
                 Master Boot Record (MBR)
                          │
      ┌───────────────────┼───────────────────┐
      │                   │                   │
      ▼                   ▼                   ▼
+-------------+    +-------------+    +-------------+
| Partition 1 |    | Partition 2 |    | Partition 3 |
| (Bootable)  |    |             |    |             |
+-------------+    +-------------+    +-------------+
      │
      ▼
Searches for GRUB
      │
      ▼
Loads GRUB into RAM
```

### Responsibilities of the MBR

- Located in the first sector of the disk.
- Stores the partition table.
- Identifies the active (bootable) partition.
- Loads the boot loader (such as **GRUB**) into memory.
- Passes control to the boot loader.

### What is GRUB?

**GRUB (Grand Unified Bootloader)** is the most common Linux boot loader.

Its responsibilities are:

- Displays the boot menu.
- Lets you choose an operating system if multiple are installed.
- Loads the Linux kernel into memory.
- Passes control to the Linux kernel.

- Passes control to the Linux kernel.

### In Simple Words

Think of the boot process like entering a building:

```text
Power Button
      │
      ▼
BIOS
(Security Guard)
      │
      ▼
MBR
(Building Directory)
      │
      ▼
GRUB
(Receptionist)
      │
      ▼
Linux Kernel
(Main Office)
```

The BIOS checks the hardware, the MBR points to the boot loader, the boot loader loads the Linux kernel, and then the operating system starts.



### Boot Loader in Action

Once the **Boot Loader (GRUB)** starts, it performs the following steps:

```text
        System
           │
           ▼
   Bootable Hard Disk
           │
           ▼
      Boot Loader
        (GRUB)
       ┌────┴────┐
       ▼         ▼
 Linux Kernel   Initial RAM Disk (initramfs)
```

### What Happens?

1. The BIOS loads the **MBR**.
2. The **MBR** loads **GRUB (Boot Loader)**.
3. GRUB loads:
   - The **Linux Kernel**.
   - The **Initial RAM Disk (initramfs/initrd)** into RAM.
4. The kernel starts using the temporary filesystem from the Initial RAM Disk.
5. The kernel then mounts the real root filesystem.
6. Finally, it starts the first userspace process: **`/sbin/init`** (or **systemd** on modern Linux).


### What is the Initial RAM Disk (initramfs)?

The **Initial RAM Disk (initramfs)** is a temporary filesystem loaded into RAM before the real operating system starts.

Its job is to:

- Load essential drivers.
- Detect storage devices.
- Mount the real root filesystem.
- Hand control to the Linux operating system.

### Complete Boot Flow

```text
Power On
    │
    ▼
BIOS
    │
    ▼
MBR
    │
    ▼
GRUB (Boot Loader)
    │
    ├──────────────┐
    ▼              ▼
Linux Kernel   initramfs
      │             │
      └──────┬──────┘
             ▼
     Mount Root Filesystem
             │
             ▼
      /sbin/init (systemd)
             │
             ▼
     Linux Userspace Starts
```


### What is Inside initramfs?

`initramfs` is a small temporary filesystem loaded into **RAM** by the boot loader.

### In Simple Words

Think of **initramfs** as an **emergency toolkit** carried by the boot loader.

When the kernel wakes up:

- It doesn't yet know where the real operating system is.
- The toolkit contains just enough tools to find the hard drive.
- It loads the required drivers.
- It mounts the real Linux filesystem.
- Then the toolkit is discarded, and Linux continues booting normally.

## Text Mode Login

After the kernel finishes booting and mounts the root filesystem, it starts the first userspace process:

```
Kernel
   │
   ▼
/sbin/init (or systemd)
   │
   ▼
Starts System Services
   │
   ▼
getty
   │
   ▼
Login Prompt (TTY)
```

### What is `/sbin/init`?

`/sbin/init` (or **systemd** on modern Linux) is **Process ID 1 (PID 1)**.

It is the first process started by the Linux kernel.

Its responsibilities include:

- Starting system services.
- Mounting remaining filesystems.
- Managing background processes (daemons).
- Starting login terminals.
- Starting the graphical desktop (if installed).

---

### What is `getty`?

`getty` is a program started by **systemd/init**.

Its job is to:

- Display the login prompt.
- Accept the username.
- Start the login program.
- Launch the user's shell after successful authentication.

Example:

```text
Ubuntu 24.04 LTS

login: aryan
Password: ********
```

After successful login:

```bash
aryan@ubuntu:~$
```

You are now inside the Linux shell.

---

### What is TTY?

TTY (Teletype Terminal) is a **text-based virtual terminal**.

Linux usually provides multiple virtual terminals:

- Ctrl + Alt + F1
- Ctrl + Alt + F2
- Ctrl + Alt + F3
- ...
- Ctrl + Alt + F6

Each TTY provides an independent text login session.

---

### Boot Flow Until Text Login

```text
Power On
    │
BIOS
    │
MBR
    │
GRUB
    │
Linux Kernel
    │
initramfs
    │
Mount Root Filesystem
    │
systemd (/sbin/init)
    │
Start Services
    │
getty
    │
Text Login Prompt
```

---

### In Simple Words

Think of **systemd** as the **manager of a company**.

- The **Kernel** hires the manager (**systemd**).
- The manager starts every department (services).
- One employee (**getty**) sits at the reception desk.
- When you enter your username and password, getty welcomes you and opens your workspace (the shell).

# Filesystem Hierarchy Standard (FHS)

The **Filesystem Hierarchy Standard (FHS)** defines the standard directory structure used by Linux systems.

It specifies:
- Where system files should be stored.
- Where user files should be stored.
- Where applications should install files.
- Where logs, configuration files, and devices are located.

The goal is to keep all Linux distributions organized in a consistent way.