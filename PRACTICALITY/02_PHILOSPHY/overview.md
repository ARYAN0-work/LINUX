## first commands 

man ls
man mkdir 

> KERNEL

Kernel = brain of Linux OS, controls hardware and helps applications interact with hardware.

> DISTURBUTIONS 

Linux Distribution
│
├── Linux Kernel
├── Libraries
├── GNU/Linux utilities
├── Shell
├── Package manager
├── System services
├── Configuration
├── Applications
└── GUI (optional)

So: Kernel ≠ Distribution

Ubuntu is a distribution.

Ubuntu contains a Linux kernel plus a large collection of user-space software.

> Boot loader =>

Power ON
   ↓
Firmware (UEFI/BIOS)
   ↓
Boot Loader
   ↓
Linux Kernel
   ↓
Init/System Manager
   ↓
Services
   ↓
System ready

- What does the bootloader actually do?

Its main job is to load/start the kernel and hand control over to it.

GRUB is a common example.

For your WSL environment, though, you generally won't be manually dealing with GRUB, because WSL's startup mechanism is different from booting a normal physical Linux installation.

> Service: A program that runs in the background.

For example, an SSH server

> Filesystem: A filesystem is the way Linux stores and organizes files.

Disk
 ↓
Filesystem
 ↓
Directories + Files

# Important distinction
A disk and a filesystem aren't the same thing.

> X Window System / X11

X11 (X Window System) is a graphical windowing system/protocol that provides mechanisms for graphical applications, windows, input, and display.

Modern Linux desktops can also use Wayland, which is why your notes correctly mention: X11 / Wayland

> Window Manager (WM)

Controls how windows behave and are arranged.

Things like:

moving windows
resizing
stacking
focusing
tiling, depending on the WM

> Desktop Environment (DE)

The whole graphical desktop experience.

````bash
CLI = Command-Line Interface

It's the interface through which you interact by typing commands.

````

```bash

Shell

The shell is the program that interprets your commands.

```

### You
 ↓
CLI
 ↓
Bash
 ↓
Kernel
 ↓
Hardware

You type:
mkdir project
     ↓
Bash interprets it
     ↓
Bash invokes the appropriate program/system calls
     ↓
Kernel handles the underlying operations

- PowerShell is a shell that provides a CLI experience.


### SUMMARY => 

                    USER
                     │
                     ▼
              CLI / GUI
               │       │
               │       └──────────────┐
               ▼                      ▼
             Shell              Desktop Environment
             Bash                    │
               │                     ▼
               │                X11 / Wayland
               │                     │
               └──────────┬──────────┘
                          ▼
                       KERNEL
                          │
                          ▼
                      HARDWARE