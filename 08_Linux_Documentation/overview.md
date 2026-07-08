# Linux Documentation - Overview

## Goal
Linux provides multiple ways to get help and documentation directly from the terminal. Knowing where to find information is more important than memorizing every command.

---

## Topics Covered

### 1. Manual Pages (man)
- Primary source of Linux command documentation.
- Explains:
  - Command description
  - Syntax
  - Options
  - Examples
- Example:
  ```bash
  man ls
  ```

---

### 2. Built-in Help (--help)
- Quick way to view command usage.
- Useful for common options.
- Example:
  ```bash
  ls --help
  cp --help
  ```

---

### 3. Info Pages
- More detailed and structured documentation than `man`.
- Supports navigation between sections.
- Example:
  ```bash
  info ls
  ```

---

### 4. Documentation Files
Many applications store documentation inside:

```text
/usr/share/doc/
```

This may include:
- README files
- License
- Configuration examples
- User guides

---

### 5. Shell Help
For shell built-in commands, use:

```bash
help
```

Example:

```bash
help cd
help echo
```

---

### 6. Finding Documentation
Useful commands:

```bash
man command
command --help
info command
help command
```

---

## Why Documentation Matters

Instead of memorizing hundreds of Linux commands:

- Learn how to search.
- Read documentation.
- Experiment with commands.
- Practice regularly.

Professional Linux users constantly refer to documentation.

---

# Summary

Linux provides several documentation sources:

- `man` → Complete manual pages
- `--help` → Quick command help
- `info` → Detailed documentation
- `help` → Shell built-in commands
- `/usr/share/doc/` → Package documentation

The best Linux skill isn't memorizing commands—it's knowing where to find reliable information quickly.