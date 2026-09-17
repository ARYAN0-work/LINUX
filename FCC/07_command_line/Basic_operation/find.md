# `find` Command

The `find` command is used to search for files and directories in a directory hierarchy. It is one of the most powerful Linux commands because it can search based on name, type, size, permissions, owner, and much more.

---

## Syntax

```bash
find [path] [options] [expression]
```

- `path` → Directory where the search starts.
- `options` → Modify how `find` behaves.
- `expression` → Conditions that files/directories must satisfy.

---

# `-name`

The `-name` option searches for files or directories whose names match a specific pattern.

## Syntax

```bash
find [path] -name "pattern"
```

---

## Examples

### Find a file by its exact name

```bash
find . -name "notes.txt"
```

Searches the current directory (`.`) and all its subdirectories for a file named `notes.txt`.

---

### Find a directory by name

```bash
find . -name "Documents"
```

Searches for a directory (or file) named `Documents`.

---

### Find all Markdown files

```bash
find . -name "*.md"
```

Finds every file ending with `.md`.

---

### Find all shell scripts

```bash
find . -name "*.sh"
```

Finds every file ending with `.sh`.

---

### Search from the root directory

```bash
find / -name "config.json"
```

Searches the entire filesystem for `config.json`.

> **Note:** You may need `sudo` to access protected directories.

```bash
sudo find / -name "config.json"
```

---

## Wildcards

| Pattern | Meaning |
|---------|---------|
| `*` | Matches zero or more characters |
| `?` | Matches exactly one character |

Example:

```bash
find . -name "*.txt"
```

Matches:

- `notes.txt`
- `todo.txt`
- `hello.txt`

---

## Important Notes

- `-name` is **case-sensitive**.
- Use quotes (`" "`) around wildcard patterns to prevent the shell from expanding them before `find` processes them.
- Searches recursively through all subdirectories by default.

---

## Summary

- Search files/directories by name using `-name`.
- Supports wildcard patterns (`*`, `?`).
- Searches recursively.
- Case-sensitive matching.
- Use `sudo` when searching protected locations.

---

## Quick Reference

```bash
find . -name "file.txt"      # Exact filename
find . -name "*.txt"         # All .txt files
find . -name "*.md"          # All Markdown files
find . -name "*.sh"          # All shell scripts
find / -name "config.json"   # Search entire filesystem
sudo find / -name "file"     # Search protected directories
```

# `-iname` Command

The `-iname` option works exactly like `-name`, except it performs a **case-insensitive** search.

---

## Syntax

```bash
find [path] -iname "pattern"
```

---

## Examples

### Find a file regardless of letter case

```bash
find . -iname "notes.txt"
```

Matches:

- `notes.txt`
- `Notes.txt`
- `NOTES.TXT`
- `NoTeS.TxT`

---

### Find all Markdown files

```bash
find . -iname "*.md"
```

Matches:

- `README.md`
- `readme.MD`
- `Notes.Md`

---

### Search the entire filesystem

```bash
sudo find / -iname "config.json"
```

Searches for `config.json` without considering uppercase or lowercase letters.

---

## Difference Between `-name` and `-iname`

| Option | Case Sensitive |
|---------|---------------|
| `-name` | ✅ Yes |
| `-iname` | ❌ No |

Example:

```bash
find . -name "hello.txt"
```

Matches only:

```
hello.txt
```

```bash
find . -iname "hello.txt"
```

Matches:

```
hello.txt
HELLO.TXT
Hello.txt
HeLLo.TxT
```

---

## Summary

- `-iname` performs a **case-insensitive** search.
- Supports wildcard patterns (`*`, `?`).
- Searches recursively through subdirectories.
- Useful when you're unsure about filename capitalization.

---

## Quick Reference

```bash
find . -iname "file.txt"
find . -iname "*.md"
find . -iname "*.jpg"
sudo find / -iname "config.json"
```

---

# `-type` Command

The `-type` option filters search results based on the type of filesystem object (file, directory, link, etc.).

---

## Syntax

```bash
find [path] -type [type]
```

---

## Common Types

| Type | Meaning |
|------|---------|
| `f` | Regular file |
| `d` | Directory |
| `l` | Symbolic link |
| `c` | Character device |
| `b` | Block device |
| `p` | Named pipe (FIFO) |
| `s` | Socket |

---

## Examples

### Find only regular files

```bash
find . -type f
```

---

### Find only directories

```bash
find . -type d
```

---

### Find only symbolic links

```bash
find . -type l
```

---

### Find all Markdown files only

```bash
find . -type f -name "*.md"
```

---

### Find all directories named "src"

```bash
find . -type d -name "src"
```

---

### Find executable shell scripts

```bash
find . -type f -name "*.sh"
```

---

## Combining `-type` with Other Options

Find all text files:

```bash
find . -type f -name "*.txt"
```

Find all directories ending with "backup":

```bash
find . -type d -name "*backup"
```

Find all symbolic links:

```bash
find . -type l
```

---

## Summary

- `-type` filters search results by object type.
- Most commonly used values:
  - `f` → Regular file
  - `d` → Directory
  - `l` → Symbolic link
- Often combined with `-name`, `-iname`, or other search options.

---

## Quick Reference

```bash
find . -type f
find . -type d
find . -type l
find . -type f -name "*.txt"
find . -type d -name "src"
find . -type f -iname "*.md"
```