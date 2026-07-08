# GNU Info (`info`)

## What is GNU Info?

GNU Info is another documentation system in Linux.

Unlike `man`, Info organizes documentation into linked pages (nodes), making it easier to navigate large manuals.

It is commonly used for GNU software.

---

## Basic Syntax

```bash
info <command>
```

Example:

```bash
info ls
info bash
info coreutils
```

---

## Why Use Info?

- More detailed than `man`
- Organized into chapters and sections
- Supports hyperlinks between topics
- Better for learning complex programs

---

## Navigation

| Key | Action |
|------|--------|
| ↑ / ↓ | Move line by line |
| Space | Next page |
| Backspace | Previous page |
| Enter | Open selected link |
| n | Next node |
| p | Previous node |
| u | Go to parent node |
| l | Go back to previous node |
| q | Quit |

---

## Difference Between `man` and `info`

| Feature | `man` | `info` |
|---------|-------|--------|
| Purpose | Quick reference | Detailed documentation |
| Structure | Single manual page | Linked documentation |
| Navigation | Linear | Menu-based |
| Best For | Looking up commands | Learning software in depth |

---

## Example

View the documentation for `ls`:

```bash
info ls
```

View Bash documentation:

```bash
info bash
```

---

# Summary

| Command | Purpose |
|---------|---------|
| `info ls` | Open Info page for `ls` |
| `info bash` | Open Bash documentation |
| `q` | Quit |
| `n` | Next node |
| `p` | Previous node |
| `u` | Parent node |
| `l` | Last visited node |

---

## Key Takeaway

- **`man`** → Quick command reference.
- **`info`** → Detailed, book-like documentation with navigation.
- Use `man` for everyday command lookup and `info` when you need a deeper explanation.