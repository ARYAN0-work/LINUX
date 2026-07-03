

# Understanding `su`, `sudo`, Root User, and WSL

## What I Tried

I was learning Linux command-line operations and wanted to understand the `su` command.

I ran:

```bash
su
```

Linux prompted me for a password:

```text
Password:
su: Authentication failure
```

Since I couldn't remember my password, I assumed I had forgotten it.

---

# What Was Actually Happening

The important thing to understand is that **`su` does not ask for my user password.**

Instead, it asks for the **password of the user I want to become.**

When I simply type:

```bash
su
```

Linux assumes:

```bash
su root
```

which means:

> "Switch to the **root** user."

Therefore, Linux expects the **root user's password**, **not my own password**.

---

# Why It Failed

I am using **Ubuntu on WSL2 (Windows Subsystem for Linux)**.

I verified this using:

```bash
uname -a
```

Output:

```text
Linux LAPTOP-JKAF7PUH 6.6.87.2-microsoft-standard-WSL2 ...
```

The important part is:

```text
microsoft-standard-WSL2
```

This confirms that I'm running Ubuntu inside **WSL2**.

---

# How Ubuntu Handles Root

Ubuntu does **not** encourage logging in directly as the root user.

Instead, Ubuntu recommends using:

```bash
sudo
```

The root account usually **does not have a password configured** by default.

Because of this:

```bash
su
```

fails with:

```text
Authentication failure
```

This does **not** mean my own password is incorrect.

It simply means that **the root account cannot authenticate using `su` because no root password has been set.**

---

# The Correct Way

Instead of:

```bash
su
```

Ubuntu expects me to use:

```bash
sudo <command>
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

# Becoming the Root User

If I really need a root shell, I should use:

```bash
sudo -i
```

After entering **my own user password**, Linux switches me to the root account.

Example:

```text
aryan@LAPTOP-JKAF7PUH:~$ sudo -i
[sudo] password for aryan:
root@LAPTOP-JKAF7PUH:~#
```

Notice the prompt changes:

Normal user:

```text
$
```

Root user:

```text
#
```

The `#` indicates administrator (root) privileges.

---

# WSL-Specific Method

Since I'm using WSL, I can also start Ubuntu directly as the root user from **PowerShell**.

Command:

```powershell
wsl --user root
```

This launches Ubuntu directly into:

```text
root@LAPTOP-JKAF7PUH#
```

This method is **specific to WSL** and does not exist on normal Linux servers.

---

# Difference Between `su` and `sudo`

| `su`                                               | `sudo`                                             |
| -------------------------------------------------- | -------------------------------------------------- |
| Switches to another user                           | Runs a single command with elevated privileges     |
| Requires the target user's password (usually root) | Requires my own password                           |
| Opens a shell as another user                      | Executes one command as root                       |
| Less commonly used on Ubuntu                       | Recommended by Ubuntu and most Linux distributions |

---

# Command Structure

## `su`

```bash
su
```

Equivalent to:

```bash
su root
```

Meaning:

```text
Become the root user.
```

---

## `sudo`

```bash
sudo apt install nginx
```

Breakdown:

```text
┌──────────┬─────────┬────────────┬──────────┐
│ Command  │ Command │ Subcommand │ Argument │
├──────────┼─────────┼────────────┼──────────┤
│ sudo     │ apt     │ install    │ nginx    │
└──────────┴─────────┴────────────┴──────────┘
```

Here:

* `sudo` gives administrator privileges.
* `apt` is the package manager.
* `install` tells `apt` what action to perform.
* `nginx` is the package to install.

---

# My Mistakes

### ❌ Mistake 1

I thought `su` was asking for **my password**.

Reality:

It was asking for the **root user's password**.

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

which confirmed I was using **WSL2**.

---

### ❌ Mistake 3

I ran:

```bash
wsl --user root
```

inside Ubuntu.

That failed because:

`wsl` is a **Windows command**, not a Linux command.

It must be executed from:

```text
PowerShell
```

or

```text
Command Prompt
```

---

# Important Commands Learned

Check Linux version:

```bash
uname -a
```

Become root (recommended):

```bash
sudo -i
```

Run one command as root:

```bash
sudo <command>
```

Exit the root shell:

```bash
exit
```

Launch WSL as root (PowerShell):

```powershell
wsl --user root
```

---

# Key Takeaways

* `su` asks for the **target user's password** (usually root).
* `sudo` asks for **my own password**.
* Ubuntu prefers `sudo` over `su`.
* WSL is still real Linux, but it has a few Windows-specific features.
* The prompt ending with `$` means I'm a normal user.
* The prompt ending with `#` means I'm the root user.
* I should use `sudo` for almost all administrative tasks instead of logging in as root.
