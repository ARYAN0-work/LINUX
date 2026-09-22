# Section 2 concepts you've now locked

- Kernel → manages core OS/hardware resources
- Distribution → complete Linux environment around the kernel
- Bootloader → loads/starts the kernel
- Service → background program providing functionality
- Filesystem → organizes/stores files
- X11/Wayland → graphical display infrastructure
- Window Manager → manages window behavior
- Desktop Environment → complete graphical desktop experience
- CLI → text-based interface
- Shell → program that interprets commands
- Bash → the shell we'll primarily use in WSL
- man → documentation/manual

## Q&A Revision
Question 1

Q: You type:

mkdir project

Explain the journey from you typing the command to the directory being created.

Your answer:

mkdir -> cli -> bash -> kernel and then output

🟢 What you got right

You correctly identified the important components:

CLI
 ↓
Bash
 ↓
Kernel

Your mental model was fundamentally correct.

🟡 Small correction

mkdir isn't something that comes after CLI as another interface.

mkdir is the command/program you're invoking through the shell.

A better simplified model:

You
 ↓
CLI
 ↓
Bash
 ↓
mkdir
 ↓
Kernel
 ↓
Filesystem
 ↓
project created
🔑 Lesson
CLI    = interface
Bash   = interprets commands
mkdir  = command/program
Kernel = handles underlying OS operations
Question 2

Q: Can a Linux server run applications without a GUI?

Your answer:

"yes because it's command based while GUI basically gives us visual interpretation"

🟢 Correct!

A Linux server does not need a graphical desktop to run applications.

You can interact with it through:

SSH
 ↓
Terminal
 ↓
Shell
 ↓
Commands / Applications
 ↓
Kernel

GUI is simply another way of interacting with the system.

GUI → graphical interaction
CLI → text interaction
🔑 DevOps connection

This is extremely important because many cloud servers are managed primarily through:

SSH + CLI

rather than a graphical desktop.

Question 3

Q: You're using Bash and type:

ls

Who interprets the command?

Your answer:

B

B = Bash

🟢 Correct!

Bash is the shell.

You type:
ls
 ↓
Bash interprets it
 ↓
executes the appropriate command
 ↓
output
🔑 Remember

The kernel doesn't sit there thinking:

"Oh, ls means list files."

Bash handles the shell-command interpretation.