# Man Pages (`man`)

## What is `man`?

`man` (manual) is the built-in Linux documentation system.

It provides detailed information about commands, system calls, libraries, configuration files, and more.

---

## Basic Syntax

```bash
man <command>
```

Example:

```bash
man ls
man cp
man mkdir
```

---

## Searching for a Manual

Search all manual pages for a keyword.

```bash
man -k <keyword>
```

Example:

```bash
man -k socket
```

Output:

```
socket (2)
socket (3p)
socket (7)
```

Each result belongs to a different manual section.

---

## Search Using Description

Search command descriptions for a keyword.

```bash
man -f <command>
```

or

```bash
whatis <command>
```

Example:

```bash
man -f socket
```

Output:

```
socket (7) - Linux socket interface
```

---

## Display a Specific Section

If multiple manual pages exist, specify the section number.

```bash
man <section> <command>
```

Example:

```bash
man 7 socket
man 2 socket
```

---

## Show All Matching Manual Pages

Display every matching manual page one after another.

```bash
man -a <command>
```

Example:

```bash
man -a socket
```

Press:

- `Enter` → View next page
- `Ctrl + D` → Skip
- `Ctrl + C` → Quit

---

## Manual Sections

| Section | Description |
|----------|-------------|
| 1 | User commands |
| 2 | System calls |
| 3 | Library functions |
| 4 | Devices |
| 5 | File formats & configuration |
| 6 | Games |
| 7 | Miscellaneous |
| 8 | System administration commands |

Example:

```bash
man 5 passwd
```

Shows documentation for the `passwd` file format.

---

## Useful Navigation

Inside a man page:

| Key | Action |
|-----|--------|
| ↑ / ↓ | Scroll |
| Space | Next page |
| b | Previous page |
| /word | Search |
| n | Next search result |
| N | Previous search result |
| q | Quit |

---

# Summary

| Command | Purpose |
|---------|---------|
| `man ls` | Open manual page |
| `man -k socket` | Search by keyword |
| `man -f socket` | Show short description |
| `whatis socket` | Same as `man -f` |
| `man 7 socket` | Open a specific section |
| `man -a socket` | View all matching pages |