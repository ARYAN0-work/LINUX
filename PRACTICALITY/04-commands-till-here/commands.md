# 🐧 Linux Commands — Sections 01–04

This file contains the important Linux commands and concepts learned so far.

---

# 1. Navigation

## `pwd`

Shows the current working directory.

# ls

Lists files and directories.

You can also inspect a specific directory:

ls /etc
ls /var
ls /dev
ls /proc
ls /boot

```bash
cd

Changes the current directory.

cd /home/aryan

Go one directory up:

cd ..

Go to the user's home directory:

cd ~

```


```bash
mkdir

Creates a directory.

mkdir project
mkdir -p

Creates parent directories if they don't already exist.

mkdir -p company/backend/api

Creates:

company/
└── backend/
    └── api/
```


```bash
Working With Files / Output
cat

Displays the contents of a file.

cat hello.txt

Can also be used to inspect virtual files in /proc:

cat /proc/cpuinfo
cat /proc/meminfo
cat /proc/swaps
head

Shows the beginning of a file or command output.

head file.txt

By default, shows the first 10 lines.

Show a specific number of lines:

head -5 file.txt
head -20 file.txt
```


```bash
man

Opens the manual/documentation for a command.

man ls
man mkdir
man grep

Exit the manual:

q
```

```bash
4. Privileges
sudo

Runs a command with elevated/superuser privileges.

Example:

sudo apt install nginx

Mental model:

Normal User
     ↓
   sudo
     ↓
Elevated privileges

sudo is commonly required when modifying protected system resources.
```



```bash
apt

High-level package manager used by Debian/Ubuntu-based distributions.

Example:

sudo apt install nginx

Other common commands:

sudo apt update
sudo apt upgrade

Mental model:

Ubuntu / Debian
       ↓
      apt
       ↓
     .deb
       ↓
    dpkg


dpkg

Low-level package management tool for .deb packages.

Example:

sudo dpkg -i package.deb
apt vs dpkg
apt
 ↓
High-level package management
 ↓
Downloads packages
 ↓
Handles dependencies
 ↓
Uses dpkg underneath
dpkg
 ↓
Low-level package management
 ↓
Works directly with .deb packages
```

```bash
Disk & Filesystem
df

Shows disk/filesystem space usage.

df

Human-readable output:

df -h

Show filesystem type:

df -T

Show filesystem type + human-readable sizes:

df -Th

Check the root filesystem:

df -Th /

Example:

Filesystem   Type   Size   Used   Avail   Use%   Mounted on
/dev/sda1    ext4    50G    20G     28G    42%   /

Important:

df
 ↓
Disk/filesystem usage
lsblk

Shows block devices, disks and partitions.

lsblk

Example:

NAME   SIZE TYPE MOUNTPOINT
sda     30G disk
├─sda1  28G part /
└─sda2   2G part [SWAP]

Mental model:

/dev/sda
    │
    ├── /dev/sda1
    ├── /dev/sda2
    └── /dev/sda3

/dev/sda → storage device

/dev/sda1 → partition 1 on that device

/dev/sda2 → partition 2 on that device
```

```bash
Pipes
|

The pipe sends the output of one command into another command.

Example:

ls /usr/bin | head

Flow:

ls /usr/bin
     ↓
   output
     ↓
     |
     ↓
   head
     ↓
first 10 lines

Another example:

ps aux | grep node

This concept becomes extremely important for Linux administration and troubleshooting.
```

```bash
8. Important Linux Filesystem Locations

These are not commands, but they are important locations we learned.

/
├── /home
├── /etc
├── /usr
├── /var
├── /dev
├── /proc
├── /boot
├── /tmp
├── /root
└── ...
/

Root directory.

The starting point of the Linux filesystem hierarchy.

/home

Contains normal users' home directories.

Example:

/home/aryan
/etc

Contains system-wide configuration files.

Examples:

/etc/hosts
/etc/passwd
/etc/apt
/etc/ssh
/usr

Contains many user programs, libraries and shared data.

/var

Contains variable/changing data.

Examples:

/var/log
/var/cache

Logs commonly live under:

/var/log
/dev

Contains device nodes/interfaces.

ls /dev

Important:

/dev means devices, not "development".

/proc

A virtual filesystem provided by the Linux kernel.

It exposes live system/kernel information such as:

CPU
Memory
Processes
Kernel information

Examples:

cat /proc/cpuinfo
cat /proc/meminfo
cat /proc/swaps
/boot

Contains boot-related files on traditional Linux installations.

WSL may behave differently because WSL does not boot like a traditional physical Linux installation.

/root

The home directory of the root user.

Important distinction:

/       → root directory

/root   → root user's home directory
```

```bash
Partitions & Storage

Important mental model:

Disk
 ↓
Partition
 ↓
Filesystem
 ↓
Mount point

Example:

/dev/sda1
    ↓
   ext4
    ↓
    /

Common naming:

/dev/sda  → first disk
/dev/sdb  → second disk
/dev/sdc  → third disk

/dev/sda1 → partition 1 on first disk
/dev/sda2 → partition 2 on first disk
```

```bash
10. Swap

Swap is disk storage used as overflow when RAM is under pressure.

RAM
 ↓
RAM becomes full
 ↓
Less-used memory pages
 ↓
Swap

Swap is much slower than RAM.

Swap can exist as:

A partition
A file

For now, only remember the concept.

11. MBR & GPT
MBR

Older partitioning scheme.

Important limitation:

Maximum 4 primary partitions

Extended partitions were used as containers for logical partitions.

Disk
├── Primary
├── Primary
├── Primary
└── Extended
    ├── Logical
    ├── Logical
    └── Logical
GPT

Modern partition table scheme.

It removes the old 4-primary-partition limitation and supports many partitions.

For DevOps purposes, understand the concept rather than memorizing the internals.
```

12. Quick Command Cheat Sheet
Navigation
pwd
ls
cd
mkdir
mkdir -p
Files / Output
cat
head
Documentation
man
Privileges
sudo
Packages
apt
dpkg
Storage
df
df -h
df -Th
df -Th /
lsblk
Command composition
|
🧠 Mental Map
NAVIGATION
├── pwd       → where am I?
├── ls        → what's here?
├── cd        → move
└── mkdir     → create directory

FILES / OUTPUT
├── cat       → display contents
└── head      → display beginning

DOCUMENTATION
└── man       → read command documentation

PRIVILEGES
└── sudo      → elevated privileges

PACKAGES
├── apt       → high-level package management
└── dpkg      → low-level .deb management

STORAGE
├── df        → filesystem usage
└── lsblk     → disks/partitions

COMMAND COMPOSITION
└── |         → pipe output into another command
🎯 Current Learning Priority
Must Know
pwd
ls
cd
mkdir
cat
head
man
sudo
apt
df
lsblk
|
Know Conceptually
dpkg
/proc
swap
MBR
GPT
partitions
filesystem
mount points
Don't Memorize Yet
/proc/swaps internals
MBR internals
GPT internals
bootloader internals
kernel internals
hundreds of command options

The goal is not to memorize Linux.

The goal is to understand the Linux system well enough to operate, troubleshoot and deploy applications on Linux servers.


This is the version I'd keep in your `PRACTICALITY/04-commands-till-here/co