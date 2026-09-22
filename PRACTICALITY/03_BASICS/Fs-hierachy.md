> / ->is called the root directory, It is the top of the Linux filesystem tree.

```bash
/
├── home
├── etc
├── usr
├── var
├── boot
├── dev
└── proc

/ = Entire city , /home/aryan => is like your own house inside that city.
```

> /home contains the home directories of regular users.

````bash

For you: /home/aryan is your personal Linux workspace.

So when you open your WSL terminal and see something like:aryan@LAPTOP:~$

the ~ usually represents your home directory.

For verifying: use pwd

````

> So: /etc = system-wide configuration

- Not simply "all Linux settings."

cat /etc/hosts, will show hostname mappings.

# Don't memorize:

>/usr = installed software

Instead:

>/usr = a major part of the Linux user-space software hierarchy.

````bash

You might find commands such as:

/usr/bin/git
/usr/bin/python3
/usr/bin/vim

So if you get: which git

you may get: which git

````

> /boot: This contains files needed during the boot process.

# /var ; var = variable data, It contains data that changes while the system is running.

````bash
For example:

/var/log
/var/cache

Logs are especially important.

For example, on systems using traditional system logging:

/var/log/

might contain logs from different services.

Think:

/var
 ↓
Data that changes over time
 ↓
logs
cache
spools
databases/application data (depending on setup)

Later, when something breaks on a server, you'll often be looking around places like /var/log.

````

> /dev — contains device nodes/interfaces through which programs can interact with devices.

> /proc => /proc is a virtual filesystem.

- It isn't simply a normal directory containing files stored permanently on your SSD.

- The kernel exposes information through it while the system is running.

````bash
/proc
 ↓
Kernel's live information
 ↓
CPU
Memory
Processes
Kernel information
...

````

## SUMMARY =>

/
│
├── home/     → users' home directories
│
├── etc/      → system-wide configuration
│
├── usr/      → user-space programs/libraries/data
│
├── var/      → variable data, logs, caches, etc.
│
├── boot/     → boot-related files
│
├── dev/      → device interfaces/nodes
│
└── proc/     → virtual filesystem exposing live kernel/process info

**why imp for devops**

```bash
Why this matters for DevOps

Imagine your Node.js API is running on a Linux server and suddenly something breaks.

You might investigate:

/etc/       → configuration
/var/log/   → logs
/usr/bin/   → installed commands
/proc/      → system/process information
/dev/       → devices/storage
/home/      → user/project files

You're not just memorizing folders.

You're learning:

"If I have a particular problem, where should I look?"

That's the real skill.
```

## EXTRA

```bash

pwd full form = Print Working Directory

It tells you:

- "Where am I right now in the filesystem?"

You ran: pwd and got: /home/aryan

- So you're currently here:

/
└── home
    └── aryan   ← YOU ARE HERE

```

|          | `/`                                  | `/home/aryan`                   |
| -------- | ------------------------------------ | ------------------------------- |
| Meaning  | Entire filesystem                    | Your personal directory         |
| Contains | OS directories + users + system data | Your personal files             |
| Scope    | Everything                           | Just your user's area           |
| Example  | `/etc`, `/usr`, `/var`               | `DSA`, `PRAVEG`, `WorkspaceHub` |

## IMP

/etc
 ↓
System-wide configuration
 ↓
Programs/services store configuration here

## EXTRA

| = pipe

The pipe takes the output of the command on the left and sends it as input to the command on the right.

| = pipe

The pipe takes the output of the command on the left and sends it as input to the command on the right.

head normally displays the first 10 lines of its input.

So:

ls /usr/bin | head

means:

"Show me the first 10 entries from /usr/bin."

## EXTRA

You can control how many lines:

ls /usr/bin | head -5

→ first 5 lines.

ls /usr/bin | head -20

→ first 20 lines.

### EXTRA

/var/log

→ logs keep getting added/updated.

/var/cache

→ cached data can be created/removed.

/var/run

→ runtime information changes as services/processes start and stop.

### SUMMARY

> So: /etc = system-wide configuration
>/usr = a major part of the Linux user-space software hierarchy.
> /boot: This contains files needed during the boot process.
> /dev — contains device nodes/interfaces through which programs can interact with devices.
> /proc => /proc is a virtual filesystem.


/etc/       → configuration
/var/log/   → logs
/usr/bin/   → installed commands
/proc/      → system/process information
/dev/       → devices/storage
/home/      → user/project files