# Step 1: BIOS (Basic Input/Output System)

The **BIOS (Basic Input/Output System)** is the first software that runs when a computer is powered on. It is stored on the motherboard and is responsible for initializing the hardware before handing control over to the operating system.

## Boot Sequence

```text
Power On
    │
    ▼
BIOS
(Basic Input/Output System)
    │
    ▼
Initializes hardware
(Screen, Keyboard, Memory)
```


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

It contains:

- Essential programs
- Binary files
- Basic drivers
- Kernel modules
- Startup scripts

These are enough to let the Linux kernel continue booting.

### Responsibilities of initramfs

- Mount the real root filesystem.
- Provide basic kernel functionality.
- Detect storage devices (SSD, HDD, NVMe, USB).
- Load required drivers and kernel modules.
- Check and repair the root filesystem if needed.
- Hand control over to the real operating system.

```text
           initramfs
                │
      ┌─────────┴─────────┐
      │                   │
 Programs             Binary Files
      │                   │
      └─────────┬─────────┘
                │
   ┌────────────┼────────────┐
   │            │            │
Mount Root   Detect      Load Drivers
Filesystem   Devices     & Modules
                │
                ▼
      Start the Real Linux System
```

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

---

## Filesystem Hierarchy

```text
/
├── bin
├── boot
├── dev
├── etc
├── home
├── lib
├── media
├── mnt
├── opt
├── sbin
├── srv
├── tmp
├── usr
├── var
├── root
└── proc
```

---

## Common Directories

| Directory | Purpose |
|-----------|---------|
| `/bin` | Essential user commands |
| `/boot` | Boot loader files and Linux kernel |
| `/dev` | Device files |
| `/etc` | System configuration files |
| `/home` | Home directories for normal users |
| `/lib` | Shared libraries and kernel modules |
| `/media` | Automatically mounted removable devices |
| `/mnt` | Temporary mount points |
| `/opt` | Optional third-party software |
| `/sbin` | System administration commands |
| `/srv` | Data served by system services |
| `/tmp` | Temporary files |
| `/usr` | User applications, libraries, documentation |
| `/var` | Variable data (logs, cache, mail, databases) |
| `/root` | Home directory of the root user |
| `/proc` | Virtual filesystem containing process and kernel information |

---

## In Simple Words

Think of Linux as a **city**.

Every folder has a specific purpose:

- `/home` → Houses
- `/etc` → Government office (configuration)
- `/boot` → Power station that starts the city
- `/usr` → Shopping mall (applications)
- `/var` → Warehouse (logs, cache, databases)
- `/tmp` → Dustbin for temporary items
- `/dev` → Hardware department
- `/proc` → Information center about the running system

# now learning FS from ubnutu