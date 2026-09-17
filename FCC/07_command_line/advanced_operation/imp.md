# `-exec` Command

The `-exec` option executes a command on every file or directory that matches the search criteria. It is commonly used with `find` to perform actions such as deleting, moving, copying, or changing permissions.

---

## Syntax

```bash
find [path] [conditions] -exec command {} \;
```

### Components

- `-exec` → Execute a command on matched files.
- `command` → The command to run (`rm`, `mv`, `cp`, `chmod`, etc.).
- `{}` → Placeholder for the matched file or directory.
- `\;` → Marks the end of the command.

> **Note:** You can also use `';'` instead of `\;` by enclosing it in quotes.

---

## Examples

### Delete all `.swp` files

```bash
find . -name "*.swp" -exec rm {} \;
```

---

### Delete all `.log` files

```bash
find . -name "*.log" -exec rm {} \;
```

---

### Copy all `.txt` files to another directory

```bash
find . -name "*.txt" -exec cp {} /backup/ \;
```

---

### Move all `.jpg` files

```bash
find . -name "*.jpg" -exec mv {} /images/ \;
```

---

### Change permission of all shell scripts

```bash
find . -name "*.sh" -exec chmod +x {} \;
```

---

### Display details of every Markdown file

```bash
find . -name "*.md" -exec ls -l {} \;
```

---

## Understanding `{}`

`{}` is replaced by the current file or directory found by `find`.

Example:

```bash
find . -name "*.txt" -exec cat {} \;
```

If `find` discovers:

```
notes.txt
todo.txt
```

It runs:

```bash
cat notes.txt
cat todo.txt
```

---

## Ending the Command

The command must end with either:

```bash
\;
```

or

```bash
';'
```

Both are valid:

```bash
find . -name "*.txt" -exec rm {} \;
```

```bash
find . -name "*.txt" -exec rm {} ';'
```

---

## Common Commands with `-exec`

| Command | Purpose |
|---------|---------|
| `rm` | Delete files |
| `cp` | Copy files |
| `mv` | Move files |
| `chmod` | Change permissions |
| `chown` | Change owner |
| `ls -l` | Show detailed information |
| `cat` | Display file contents |

---

## Summary

- `-exec` executes a command on each matched result.
- `{}` represents the matched file or directory.
- End the command using `\;` or `';'`.
- Commonly used with `rm`, `cp`, `mv`, `chmod`, and `ls`.

---

## Quick Reference

```bash
find . -name "*.swp" -exec rm {} \;
find . -name "*.log" -exec rm {} \;
find . -name "*.txt" -exec cp {} /backup/ \;
find . -name "*.jpg" -exec mv {} /images/ \;
find . -name "*.sh" -exec chmod +x {} \;
find . -name "*.md" -exec ls -l {} \;
```