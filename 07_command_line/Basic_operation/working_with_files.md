# Working with Files

Linux provides several commands to quickly view and inspect file contents without opening an editor.

---

## Common Commands

| Command | Purpose |
|---------|---------|
| `cat file.txt` | Display the entire file |
| `cat -n file.txt` | Display the file with line numbers |
| `less file.txt` | View a file page by page (scrollable) |
| `less -N file.txt` | View with line numbers |
| `head file.txt` | Show the first 10 lines |
| `head -20 file.txt` | Show the first 20 lines |
| `tail file.txt` | Show the last 10 lines |
| `tail -20 file.txt` | Show the last 20 lines |
| `tac file.txt` | Display the file in reverse order (last line first) |

---

## Examples

Display the whole file:

```bash
cat ready-for.sh
```

Display with line numbers:

```bash
cat -n ready-for.sh
```

View page by page:

```bash
less ready-for.sh
```

View with line numbers:

```bash
less -N ready-for.sh
```

Show first 10 lines:

```bash
head ready-for.sh
```

Show first 20 lines:

```bash
head -20 ready-for.sh
```

Show last 10 lines:

```bash
tail ready-for.sh
```

Show last 20 lines:

```bash
tail -20 ready-for.sh
```

Print file in reverse:

```bash
tac ready-for.sh
```

---

## Key Takeaways

- `cat` → Print the entire file.
- `cat -n` → Add line numbers.
- `less` → Read large files interactively.
- `head` → View the beginning of a file.
- `tail` → View the end of a file (great for logs).
- `tac` → Print the file from bottom to top.

---

## For Backend/DevOps ⭐⭐⭐⭐⭐

These commands are used constantly when working with servers.

- `cat` → Quick config check.
- `less` → Read long configuration files (`nginx.conf`, `.env`, logs).
- `head` → Inspect file headers.
- `tail` → Monitor log files (`tail -f app.log` is extremely common).
- `tac` → Useful when reading logs or data in reverse order.