# Linux Terminology and Examples

- Kernel -> brain of linux OS, it controls the Hardware and `helps to interact hardware with application `

### Architecture

```text
+------------------+
|   Applications   |
+------------------+
         │
         ▼
+------------------+
|      Kernel      |
+------------------+
         │
         ▼
+------------------+
|     Hardware     |
+------------------+
```
## Distribution

A **Linux Distribution (Distro)** is a complete operating system built around the **Linux Kernel**. It is a collection of software that includes the kernel, system utilities, package manager, libraries, desktop environment (optional), and applications.

┌─────────────────────────────────────────────────────────────────┐
│                    LINUX DISTRIBUTION (DISTRO)                  │
│                                                                 │
│  ┌──────────────────┐  ┌──────────────────┐  ┌───────────────┐  │
│  │   LINUX KERNEL   │  │ PACKAGE MANAGER  │  │   GNU TOOLS   │  │
│  │ (The Core Brain) │  │  (apt, dnf, etc) │  │ (ls, cd, cat) │  │
│  └──────────────────┘  └──────────────────┘  └───────────────┘  │
│                                                                 │
│  ┌──────────────────┐  ┌──────────────────┐  ┌───────────────┐  │
│  │   SHELL / CLI    │  │ SYSTEM SERVICES  │  │   GUI / DE    │  │
│  │   (Bash, Zsh)    │  │ (systemd, sshd)  │  │(Optional/GNOME)│ │
│  └──────────────────┘  └──────────────────┘  └───────────────┘  │
└─────────────────────────────────────────────────────────────────┘

### Components of a Distribution

- Linux Kernel
- System Utilities
- GNU Tools
- Package Manager
- Libraries
- Desktop Environment (optional)
- Applications

### Common Linux Distribution Families

```text
Linux Kernel
      │
      |  #distro families[collection of program combine with kernel to make linux os ]
      |
      ├── Debian #Induvial Distros 
      │     ├── Ubuntu
      │     └── Linux Mint
      │
      ├── RHEL
      │     ├── Fedora
      │     ├── CentOS
      │     └── Oracle Linux
      │
      ├── SUSE
      │     ├── SLES
      │     └── openSUSE
      │
      └── Other Distributions
```

Without a distribution, the Linux kernel alone is not enough to provide a complete operating system.

## Boot Loader

A **Boot Loader** is a program that starts when the computer is powered on. Its job is to load the **Linux Kernel** into memory and start the operating system.

The bootloader doesn't permanently connect the hardware to the kernel—instead, the bootloader acts as a temporary bridge that hands the kernel over to the hardware, and then steps out of the way.

### Responsibilities

- Starts when the computer is powered on.
- Loads the Linux Kernel into RAM.
- Passes control to the Linux Kernel.
- Can display a boot menu if multiple operating systems are installed.

### Boot Process

```text
+------------------+
|   Boot Loader    |
+------------------+
         │
         ▼
+------------------+
|   Linux Kernel   |
+------------------+
         │
         ▼
+------------------+
|   Init/Systemd   |
+------------------+
```

### Common Boot Loaders

- GRUB (Grand Unified Bootloader) ← Most common on Linux
- LILO (Legacy Linux Loader)
- systemd-boot

## Service

A **Service** (also called a **Daemon**) is a program that runs in the background and provides specific functionality to the operating system or other applications. Services usually start automatically when the system boots and continue running until they are stopped.


A Service (often called a Daemon in the Linux world) is a program that runs continuously in the background, waiting to perform tasks or handle requests without needing any human interaction.

Unlike standard apps (like VS Code or a browser) that close when you close their window, a service stays alive silently behind the scenes from the moment your computer boots up until it shuts down.

### Responsibilities

- Runs in the background without user interaction.
- Provides system or network functionality.
- Starts automatically during system boot (if enabled).
- Waits for requests from users or applications.

### Common Linux Services

| Service | Purpose |
|----------|---------|
| `httpd` | Web Server (Apache) |
| `nginx` | Web Server / Reverse Proxy |
| `sshd` | Secure Shell (SSH) Server |
| `ftpd` | FTP Server |
| `named` | DNS (Name) Server |
| `dhcpd` | DHCP Server |
| `nfsd` | Network File System (NFS) Server |
| `ntpd` | Network Time Protocol (NTP) Server |

## Filesystem

A **Filesystem** is the method used by an operating system to **store, organize, retrieve, and manage files and directories** on a storage device such as a hard disk, SSD, or USB drive.

It defines how data is arranged on disk so that the operating system can efficiently locate and access files.


### Architecture

```text
        User Data                 User Data
            │                         │
            ▼                         ▼
     +--------------+         +--------------+
     | Filesystem 1 |         | Filesystem 2 |
     +--------------+         +--------------+
            │                         │
            ▼                         ▼
     +--------------+         +--------------+
     | Partition 1  |         | Partition 2  |
     +--------------+         +--------------+
             \                 /
              \               /
               \             /
                ▼           ▼
           +--------------------+
           |   Hard Disk Drive  |
           +--------------------+
```

## X Window System

The **X Window System (X11)** is the graphical subsystem used by most Linux systems. It provides the foundation for graphical user interfaces (GUI) by managing windows, mouse input, keyboard input, and display output.

To put it in simple terms: Linux natively only knows text. If you install raw Linux, you just get a black screen with a blinking command prompt. The X Window System is the tool that tells the computer how to actually draw a visual window, trace a mouse cursor, and show colors on your monitor.


### Architecture

```text
                    GUI
+--------------------------------------+
| Desktop Environment                  |
| (GNOME / KDE Plasma / XFCE)          |
+--------------------------------------+
| Window Manager                       |
+--------------------------------------+
| X Window System (X11)                |
+--------------------------------------+

                  Console
+--------------------------------------+
| CLI / Shell                          |
+--------------------------------------+
| Linux Kernel                         |
+--------------------------------------+
| Hardware                             |
+--------------------------------------+
```


## Desktop Environment

A **Desktop Environment (DE)** is the graphical user interface (GUI) that users interact with on top of the operating system. It provides windows, icons, menus, panels, file managers, settings, and other graphical tools.

The Desktop Environment uses the **X Window System (or Wayland)** to display graphical applications.


### Architecture

```text
+--------------------------------------+
| Desktop Environment                  |
| (GNOME / KDE / XFCE / Cinnamon)      |
+--------------------------------------+
                │
                ▼
+--------------------------------------+
| X Window System / Wayland            |
+--------------------------------------+
                │
                ▼
+--------------------------------------+
| Linux Kernel                         |
+--------------------------------------+
                │
                ▼
+--------------------------------------+
| Hardware                             |
+--------------------------------------+
```

The 3 Main Parts of the Linux Graphic Stack
To understand X11, you have to see how it works with the other two pieces you wrote about:

X Window System (X11): The Foundation

What it does: It talks to the Linux Kernel to capture your hardware movements. When you move your mouse 2 inches to the right, X11 tracks those coordinates and tells the screen to update the pixels. It creates the basic boxes (windows) but doesn't style them.

The Window Manager (WM): The Coordinator

What it does: It sits on top of X11 and decides how windows behave. It adds the "Minimize, Maximize, and Close" buttons. It controls what happens when you click and drag a window around.

The Desktop Environment (DE): The Whole Experience

What it does: This is the complete package you interact with (like GNOME on your Ubuntu system). It bundles the Window Manager, the taskbars, the application menus, the settings panel, and default apps (like file managers and calculators) into a cohesive theme.

## Command Line

The **Command Line Interface (CLI)** is a text-based interface that allows users to interact with the operating system by typing commands. It provides a fast and powerful way to manage files, run programs, configure the system, and automate tasks.

### Architecture

```text
+----------------------+
|      User            |
+----------------------+
           │
           ▼
+----------------------+
| Command Line (Shell) |
+----------------------+
           │
           ▼
+----------------------+
|    Linux Kernel      |
+----------------------+
           │
           ▼
+----------------------+
|      Hardware        |
+----------------------+
```

### In Simple Words

Think of the **Command Line** as talking directly to the operating system.

- You type a command.
- The shell interprets it.
- The Linux kernel performs the requested operation.
- The result is displayed back to you.

Unlike a graphical interface, the command line lets you perform tasks quickly, automate repetitive work, and efficiently manage Linux systems.

> **Note:** The **Command Line (CLI)** is the interface, while the **Shell** (such as Bash or Zsh) is the program that reads and executes the commands you type.

In short, CLI is a general concept, while PowerShell is a specific product.

Here is the exact distinction:

CLI (Command Line Interface): This is the generic category name for any text-based interface where you type instructions instead of clicking icons. It is the opposite of a GUI (Graphical User Interface).

PowerShell: This is a specific, highly advanced shell program developed by Microsoft. It is a powerful example of a CLI tool.