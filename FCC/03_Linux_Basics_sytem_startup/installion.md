now i am gonna install ubnutu 1804 as virtual machine under VMware using redhead 7 host system running VMare player 

first create a virtual machine 

A virtual machine is literally a computer inside your computer.

You install software like:

Oracle VirtualBox (Free)
VMware Workstation Pro (Free for personal use)

Then you:

Download the Ubuntu ISO.
Click New VM.
Give it RAM (4–8 GB).
Give it CPU cores (2–4).
Create a virtual hard disk (25–50 GB).
Mount the ISO.
Boot the VM.
Install Ubuntu inside it.

The instructor is probably using VirtualBox or VMware.

This installs Ubuntu directly on your SSD.

You choose Windows or Ubuntu when the computer starts.

Windows
├── Ubuntu (WSL2)       ← DevOps work
└── Ubuntu VM           ← Learning & experimentation

give name password then host machine  then disk size  then customize hardware then finish if not on virtual machine then its gonna ask questions after loading ubnutu it will open login phase 

now command df -Th / 

df

df stands for Disk Filesystem.

It shows how much disk space each mounted filesystem is using.

-T
Shows the filesystem type. this is  ext4

output:
Filesystem Type  Size Used Avail Use% Mounted on
/dev/sdd  ext4 1007G 11G 946G 2% /

-h human readable 

Your Output Explained
Filesystem     Type  Size Used Avail Use% Mounted on
/dev/sdd       ext4 1007G 11G 946G   2%     /
/dev/sdd

This is the storage device.

Think:

Physical SSD/HDD
      │
   /dev/sdd
ext4

Filesystem format.

Like Windows uses:

NTFS

Linux commonly uses:

ext4
1007G

Total size.

You have roughly

1 TB

available for this filesystem.

11G

Already used.

946G

Free space remaining.

2%

Disk usage percentage.

Only 2% is currently used.

Mounted on
/

means this filesystem is mounted as the Linux root filesystem.

Why is yours /dev/sdd?

Since you're using WSL, the underlying storage is virtualized by Windows. So you might see devices like:

/dev/sdd

instead of the classic:

/dev/sda1

That's completely normal in WSL.

Real server example

On a physical Linux server, you might see:

Filesystem      Type Size Used Avail Use% Mounted on
/dev/sda1       ext4 50G  20G   28G  42% /
/dev/sda2       ext4 500G 80G  420G  16% /home

This tells you:

The OS is on /dev/sda1
User files are on /dev/sda2

cat

cat means:

Print the contents of a file

Example:

cat hello.txt

prints everything inside hello.txt.

/proc

Remember this?

/
├── etc
├── home
├── usr
├── var
└── proc

/proc is not a real folder on the disk.

It's a virtual filesystem created by the Linux kernel.

Think of it like a live dashboard.

It contains information about:

CPU
Memory
Running processes
Swap
Kernel
Network

Every file inside /proc is generated on demand.

/proc/swaps

This file tells Linux:

"Which swap areas are currently active?"

So

cat /proc/swaps

means

Show me all active swap devices.

Your Output
Filename      Type       Size      Used   Priority
/dev/sdc      partition  2097152   0      -2

Let's explain each column.

Filename
/dev/sdc

The storage device being used as swap.

Type
partition

Means it's an actual disk partition.

Sometimes you'll instead see

file

if Linux uses a swap file.

Size
2097152

This is in kilobytes.

Convert it:

2097152 KB
≈ 2048 MB
≈ 2 GB

So your WSL currently has about 2 GB of swap.

Used
0

Linux isn't using swap right now.

That's actually good.

Your RAM is enough.

Priority
-2

Linux uses this if multiple swap devices exist.

Higher priority gets used first.

For beginners, you can ignore this.

What is Swap?

Imagine your RAM is a classroom.

RAM

Desk 1
Desk 2
Desk 3
Desk 4

When all desks are full...

Linux says

"I'll temporarily put some students in the hallway."

That hallway is

Swap

It's space on the SSD/HDD used as overflow memory.

RAM vs Swap
RAM	Swap
Very fast	Much slower
Real memory	Disk used as memory
Preferred	Only used when needed

Linux always tries to use RAM first.

Why is swap important?

Suppose:

8 GB RAM
You open Chrome (40 tabs 😅)
VS Code
Docker
Virtual Machine

RAM becomes full.

Instead of crashing,

Linux moves less-used data into swap.

Programs continue working, just a bit slower.

WSL Note

You're using WSL, so your swap is managed by WSL itself. Seeing a /dev/sdc swap partition is normal.

Add this to your notes
## Check Active Swap

```bash
cat /proc/swaps

Shows all active swap devices/files.

Example output:

Filename      Type       Size      Used
/dev/sdc      partition  2097152   0
Swap
Acts as overflow memory when RAM is full.
Much slower than RAM because it uses disk storage.
Linux uses RAM first, then swap if necessary.
/proc/swaps is a virtual file provided by the kernel that shows currently active swap areas.