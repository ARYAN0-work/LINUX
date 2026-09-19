# Linux Documentation - Summary

## Documentation Sources

Linux provides several ways to access documentation:

- **Man Pages (`man`)** – Standard Linux manual pages.
- **GNU Info (`info`)** – Detailed documentation with linked sections.
- **Command Help (`-h`, `--help`)** – Quick usage information for commands.
- **Shell Help (`help`)** – Documentation for shell built-in commands.
- **Package Documentation** – Located in `/usr/share/doc/`.
- **Desktop Help Systems** – GUI-based help applications.
- **Online Resources** – Official documentation, community wikis, and tutorials.

---

## Man Pages

The `man` command is the primary documentation system in Linux.

Common usage:

```bash
man ls
```

Useful options:

```bash
man -k keyword      # Search by keyword
man -f command      # Show short description
man section command # Open a specific section
man -a command      # Display all matching manual pages
```

---

## GNU Info

GNU Info provides more detailed and structured documentation than `man`.

Example:

```bash
info ls
info bash
```

Best for learning large GNU applications.

---

## Command Help

Most Linux commands provide built-in help.

Examples:

```bash
ls --help
cp --help
tar --help
```

Some commands also support:

```bash
command -h
```

---

## Shell Built-in Help

For Bash built-in commands, use:

```bash
help
```

Examples:

```bash
help cd
help echo
help history
```

---

## Other Documentation

Additional documentation can be found in:

```text
/usr/share/doc/
```

You can also use:

- Official documentation
- Distribution documentation
- Community wikis
- Tutorials
- Forums

---

# Key Commands

```bash
man ls
man -k socket
man -f socket
man 7 socket
man -a socket

info ls

ls --help

help cd
```

---

# Key Takeaways

- Linux provides multiple documentation sources.
- `man` is the standard manual system.
- `info` offers detailed, navigable documentation.
- `--help` provides quick command usage.
- `help` is used for shell built-in commands.
- `/usr/share/doc/` contains package documentation.
- Online documentation is useful when local documentation is insufficient.

---

# Interview Points

Be able to explain:

- Difference between `man` and `info`
- Difference between `help` and `--help`
- Purpose of `man -k`
- Purpose of `man -f`
- Why Linux documentation is preferred over memorizing commands

**Golden Rule:**  
A good Linux user doesn't memorize every command—they know where to find accurate documentation quickly.