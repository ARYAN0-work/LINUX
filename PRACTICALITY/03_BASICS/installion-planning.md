1. Partition — what is it?

Think:

Disk = big piece of storage → partition = section of that disk

For example:

1 TB Disk
│
├── Partition 1 → /
├── Partition 2 → /home
├── Partition 3 → /var
└── Partition 4 → swap

The important distinction is:

Disk → physical/virtual storage device
Partition → section of that disk
Filesystem → format/structure placed on a partition
Mount point → where that filesystem appears in Linux's directory tree

So don't say:

/home is a partition.

More accurately:

A partition can be mounted at /home.

2. sda, sda1, sda2

This part is worth knowing.

/dev/sda

→ first storage disk

/dev/sda1

→ partition 1 on that disk

/dev/sda2

→ partition 2 on that disk

And:

/dev/sdb
/dev/sdc

would represent other storage devices in this naming scheme.

Mental model
/dev/sda
    │
    ├── /dev/sda1
    ├── /dev/sda2
    └── /dev/sda3

Disk → partitions.

That's the important part.

3. Why /, /home, /var can be separate

Imagine:

Disk
│
├── Partition A → /
├── Partition B → /home
└── Partition C → /var

You could have:

/

Operating system and system files.

/home

Your users' personal data.

/home/aryan
/home/user2
/var

Data that changes frequently:

/var/log
/var/cache
...

This separation can be useful on servers.

For example, imagine /var/log keeps growing and fills its partition.

If /var has its own partition, it doesn't directly consume the free space of the partition containing /.

That's a useful DevOps-level understanding.

4. Swap

You already have this concept.

RAM
 ↓
Full
 ↓
Swap

Swap can be a partition or a file.

You don't need to study swap partition internals right now.

Just remember:

Swap is disk storage used as overflow for memory.

5. Now the MBR stuff

This is where I'd tell you:

🟡 Learn the concept, don't go deep.

Old MBR partition tables had a limitation:

Maximum 4 primary partitions.

So they came up with:

Primary
Primary
Primary
Extended
   │
   ├── Logical
   ├── Logical
   └── Logical

Think:

Extended = container
Logical = things inside the container

That's enough.

6. GPT

Modern systems generally use GPT instead of MBR.

So:

OLD
MBR
 ↓
4 primary partition limitation
 ↓
Extended + Logical partitions

versus:

MODERN
GPT
 ↓
Supports many partitions
 ↓
No need for the old extended/logical workaround

For your DevOps learning, you don't need to memorize GPT's internal data structures.

Just know:

MBR is the older partitioning scheme; GPT is the modern one.

7. One important correction to your notes

Your notes say:

"Each partition has its own filesystem."

That's a useful simplified picture, but not always literally true.

A partition can contain a filesystem, but there are other arrangements too. For your current level, think:

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

This connects directly with what you just learned from:

df -Th /
8. The command you actually care about

Run this inside your Ubuntu VM, not your WSL terminal:

lsblk

This is much more useful for learning partitions than memorizing the examples.

You might see something like:

NAME   SIZE TYPE MOUNTPOINT
sda     30G disk
├─sda1  28G part /
└─sda2   2G part [SWAP]

Read it as:

sda
│
├── sda1 → partition → /
└── sda2 → partition → swap
Your priority

Must know ✅

Disk
Partition
Filesystem
Mount point
sda → disk
sda1 → partition
lsblk → inspect block devices/partitions
df -Th → inspect mounted filesystem usage/type

Know conceptually 🟡

MBR → old → 4 primary partitions
Extended → container
Logical → inside extended
GPT → modern partition table

Skip for now ❌

MBR internals, partition-table structures, boot-sector details, GPT internals, etc.

That's enough to move forward with Linux/DevOps.