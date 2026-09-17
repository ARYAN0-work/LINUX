Since you're learning on WSL, don't spend much time trying these shortcuts. They won't work because WSL isn't booting a full Linux desktop environment

# Switching Between GUI and Command Line (TTY)

Linux allows you to switch between the **Graphical User Interface (GUI)** and multiple **virtual command-line terminals**.

A single Linux system can have several virtual terminals running simultaneously.

```
          GUI (Desktop)
               │
      ┌────────┴────────┐
      │                 │
 Ctrl+Alt+F2       Ctrl+Alt+F3
      │                 │
     TTY2             TTY3
      │                 │
 Ctrl+Alt+F4       Ctrl+Alt+F5
      │                 │
     TTY4             TTY5
```

---

## What is a TTY?

TTY stands for **Teletype Terminal**.

Originally, Linux was designed to support multiple text terminals connected to the same system. Today, these are called **virtual terminals**.

Each TTY provides:

- A separate login session
- Its own shell
- Independent running programs

---

## Switching to a TTY

Use:

```text
Ctrl + Alt + F2
```

or

```text
Ctrl + Alt + F3
```

or

```text
Ctrl + Alt + F4
```

and so on.

Each key combination opens a different virtual terminal.

Example:

```
Ctrl + Alt + F2  →  TTY2
Ctrl + Alt + F3  →  TTY3
Ctrl + Alt + F4  →  TTY4
Ctrl + Alt + F5  →  TTY5
Ctrl + Alt + F6  →  TTY6
```

You'll usually see a login prompt like:

```text
Ubuntu 24.04 LTS

login:
```

Log in using your username and password.

---

## Returning to the GUI

Most modern Ubuntu systems use:

```text
Ctrl + Alt + F1
```

or

```text
Ctrl + Alt + F2
```

to return to the graphical desktop.

> **Note:** The exact key depends on the Linux distribution and display manager (GDM, LightDM, SDDM, etc.).

---

## Why Multiple TTYs Exist

Imagine this situation:

- GUI freezes.
- Mouse stops responding.
- Desktop becomes unusable.

Instead of restarting your computer, you can:

```
Ctrl + Alt + F3
```

Log in.

Then fix the problem from the terminal.

For example:

```bash
top
```

or

```bash
kill <PID>
```

or

```bash
sudo systemctl restart gdm
```

---

## Why Developers Use TTYs

Developers and system administrators use TTYs to:

- Recover from a frozen GUI
- Debug graphical problems
- Run servers without a desktop
- Perform system maintenance
- Access Linux remotely

Many production Linux servers don't even have a GUI—they run entirely from the command line.

---

## WSL Users

If you're using **Windows Subsystem for Linux (WSL)**, these shortcuts **do not work**.

Why?

Because WSL does **not** provide Linux virtual terminals.

Your Linux shell runs inside a Windows terminal application.

So pressing:

```text
Ctrl + Alt + F2
```

will not switch to another Linux TTY.

---

## Key Takeaways

- Linux supports multiple virtual terminals (TTYs).
- Each TTY is an independent command-line session.
- You can switch between them using `Ctrl + Alt + F2`, `F3`, `F4`, etc.
- The GUI itself runs on one of these virtual terminals.
- TTYs are useful for debugging and system administration.
- WSL does not support Linux virtual terminals.