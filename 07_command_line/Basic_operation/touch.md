# Touch, mkdir, mv & rm

These commands are used to create, rename, move, and delete files/directories.

---

## Common Commands

| Command | Purpose |
|---------|---------|
| `touch file.txt` | Create an empty file |
| `mkdir dir_name` | Create a directory |
| `mkdir -p parent/child` | Create nested directories |
| `mv old.txt new.txt` | Rename a file |
| `mv file.txt /path/` | Move a file |
| `rm file.txt` | Delete a file |
| `rm -f file.txt` | Force delete without confirmation |
| `rm -i file.txt` | Ask before deleting |
| `rm -r dir/` | Delete a directory recursively |
| `rm -rf dir/` | Force delete a directory and everything inside ⚠️ |

---

## Examples

Create an empty file:

```bash
touch notes.txt
```

Create a directory:

```bash
mkdir projects
```

Create nested directories:

```bash
mkdir -p web/backend/api
```

Rename a file:

```bash
mv old.txt new.txt
```

Move a file:

```bash
mv notes.txt Documents/
```

Delete a file:

```bash
rm notes.txt
```

Delete with confirmation:

```bash
rm -i notes.txt
```

Force delete:

```bash
rm -f notes.txt
```

Delete a directory:

```bash
rm -r projects/
```

Force delete a directory:

```bash
rm -rf projects/
```

---

## Key Takeaways

- `touch` → Creates an empty file (or updates timestamp if it already exists).
- `mkdir` → Creates directories.
- `mkdir -p` → Creates parent directories automatically.
- `mv` → Used for both **moving** and **renaming** files.
- `rm` → Deletes files.
- `rm -r` → Deletes directories recursively.
- `rm -rf` → Deletes everything **without asking** ⚠️ (be careful).

---

## For Backend/DevOps ⭐⭐⭐⭐⭐

You'll use these commands every day:

- `touch` → Create config files (`.env`, `Dockerfile`, `README.md`).
- `mkdir` → Create project folders.
- `mv` → Organize logs, backups, and deployments.
- `rm` → Remove temporary files.
- `rm -rf` → Clean build folders (`node_modules`, `dist`, `build`) **only when you're sure**.