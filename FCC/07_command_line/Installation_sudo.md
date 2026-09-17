# if not installed 

type "su" and press "Enter"

# Understanding `su`, `sudo`, `/etc/sudoers.d`, Root User, and WSL

## What Happened During the Course

While learning Linux command-line operations, the instructor asked me to type:

```bash
su
```

After typing it, he immediately started explaining:

* Root user (`#`)
* `/etc/sudoers.d/`
* Giving another user sudo privileges

I became confused because my `su` command always failed with:

```text
Password:
su: Authentication failure
```

I initially thought:

> "I forgot my password."

But that wasn't the real problem.

---

# What `su` Actually Does

`su` stands for:

> **Switch User**

When you simply type:

```bash
su
```

Linux automatically assumes:

```bash
su root
```

Meaning:

> "Switch to the **root** user."

Therefore Linux asks for:

> **The root user's password**

NOT your own password.

---

# Why My `su` Failed

I verified my Linux environment using:

```bash
uname -a
```

Output:

```text
Linux LAPTOP-JKAF7PUH 6.6.87.2-microsoft-standard-WSL2
```

The important part is:

```text
microsoft-standard-WSL2
```

which means I'm running **Ubuntu on WSL2**.

---

# Ubuntu's Design

Unlike some Linux distributions, Ubuntu disables direct root login by default.

The root account usually has **no password configured**.

Therefore:

```bash
su
```

asks for the root password...

...but no root password exists.

Result:

```text
Authentication failure
```

This **does NOT mean my user password is wrong.**

---

# The Correct Ubuntu Way

Ubuntu expects administrators to use:

```bash
sudo
```

instead of

```bash
su
```

Example:

```bash
sudo apt update
```

or

```bash
sudo apt install git
```

---

# Becoming Root Correctly

Instead of:

```bash
su
```

I should use:

```bash
sudo -i
```

Example:

```text
aryan@LAPTOP-JKAF7PUH:~$ sudo -i
[sudo] password for aryan:
root@LAPTOP-JKAF7PUH:~#
```

Notice the prompt changed:

Normal user:

```text
$
```

Root user:

```text
#
```

The `#` means I now have administrator privileges.

---

# WSL-Specific Method

Since I'm using WSL, I can also start Ubuntu directly as root from Windows PowerShell.

```powershell
wsl --user root
```

Result:

```text
root@LAPTOP-JKAF7PUH:/mnt/c/Users/aryan#
```

This command only exists because I'm using WSL.

It does **not** exist on normal Linux servers.

---

# Why The Instructor Could Continue After `su`

The instructor is **not using WSL**.

On his Linux machine:

```bash
su
```

works because he knows the root password.

After becoming root, his prompt becomes:

```text
#
```

Only then does he start modifying system configuration.

So the sequence is:

```text
Normal User ($)
        │
        ▼
      su
        │
        ▼
Root User (#)
        │
        ▼
Configure sudo
```

He is **not teaching another meaning of `su`**.

He is simply using the administrator privileges obtained through `su`.

---

# Understanding `/etc/sudoers.d`

After becoming root, the instructor runs:

```bash
echo "student ALL=(ALL) ALL" > /etc/sudoers.d/student
```

This creates a configuration file:

```text
/etc/sudoers.d/student
```

whose contents are:

```text
student ALL=(ALL) ALL
```

Meaning:

> The user **student** is allowed to run commands as any user (including root) using `sudo`.

---

# Breaking Down The Command

Command:

```bash
echo "student ALL=(ALL) ALL" > /etc/sudoers.d/student
```

Breakdown:

| Part                      | Meaning                        |
| ------------------------- | ------------------------------ |
| `echo`                    | Print text                     |
| `"student ALL=(ALL) ALL"` | The sudo rule                  |
| `>`                       | Redirect output into a file    |
| `/etc/sudoers.d/student`  | File that stores the sudo rule |

After execution, the file contains:

```text
student ALL=(ALL) ALL
```

---

# Securing The File

Next the instructor runs:

```bash
chmod 440 /etc/sudoers.d/student
```

This changes the file permissions.

Permission:

```text
440
```

Meaning:

| User   | Permission |
| ------ | ---------- |
| Owner  | Read       |
| Group  | Read       |
| Others | None       |

This prevents ordinary users from modifying sudo configuration.

---

# Why `/etc/sudoers.d/` Exists

The main sudo configuration file is:

```text
/etc/sudoers
```

Modern Linux systems recommend placing additional configuration inside:

```text
/etc/sudoers.d/
```

Advantages:

* Safer than editing `/etc/sudoers`
* Easier to manage users
* Applications can have separate configuration files
* Less chance of breaking sudo

---

# Why I Don't Need To Do This

Since I installed Ubuntu through WSL:

My user:

```text
aryan
```

was automatically added to the **sudo** group during installation.

That's why these commands already work:

```bash
sudo apt update
```

```bash
sudo apt install git
```

```bash
sudo -i
```

I don't need to manually edit:

```text
/etc/sudoers.d/
```

unless I'm administering other users.

---

# Difference Between `su` and `sudo`

| `su`                                | `sudo`                                            |
| ----------------------------------- | ------------------------------------------------- |
| Switches to another user            | Runs a command with elevated privileges           |
| Usually switches to root            | Executes only the requested command               |
| Requires the target user's password | Requires my own password                          |
| Opens a root shell                  | Returns to normal user after the command finishes |
| Less common on Ubuntu               | Recommended by Ubuntu                             |

---

# Prompt Symbols

Normal user:

```text
aryan@LAPTOP-JKAF7PUH:~$
```

Administrator:

```text
root@LAPTOP-JKAF7PUH:~#
```

Meaning:

| Symbol | Meaning              |
| ------ | -------------------- |
| `$`    | Normal user          |
| `#`    | Root (administrator) |

---

# Mistakes I Made

### ❌ Mistake 1

I thought `su` was asking for **my password**.

Reality:

It was asking for the **root password**.

---

### ❌ Mistake 2

I thought I wasn't using WSL.

Reality:

Running:

```bash
uname -a
```

showed:

```text
microsoft-standard-WSL2
```

confirming I was using WSL2.

---

### ❌ Mistake 3

I tried running:

```bash
wsl --user root
```

inside Ubuntu.

This failed because:

`wsl` is a **Windows command**, not a Linux command.

It must be executed from:

* PowerShell
* Command Prompt

---

# Commands I Learned

Check Linux version:

```bash
uname -a
```

Become root (recommended):

```bash
sudo -i
```

Run one command as administrator:

```bash
sudo <command>
```

Exit root shell:

```bash
exit
```

Launch WSL directly as root:

```powershell
wsl --user root
```

---

# Key Takeaways

* `su` means **Switch User**.
* `su` asks for the **target user's password**, usually the root password.
* `sudo` asks for **my own password**.
* Ubuntu prefers `sudo` instead of direct root login.
* WSL is a Linux environment running on Windows, so it has a few Windows-specific commands like `wsl`.
* The instructor used `su` only to become root before modifying system configuration.
* `/etc/sudoers.d/` stores additional sudo permission rules.
* The `#` prompt means I am the root user.
* The `$` prompt means I am a normal user.
* As a Backend or DevOps engineer, I will use `sudo` almost every day, while editing `/etc/sudoers.d/` is something I'll only do when managing users or configuring servers.
