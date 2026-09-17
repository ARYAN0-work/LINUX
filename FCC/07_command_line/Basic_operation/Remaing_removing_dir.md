# Renaming & Removing Directories

These commands are used to rename, create, and delete directories.

---

## Common Commands

| Command | Purpose |
|---------|---------|
| `mv old_dir new_dir` | Rename a directory |
| `mkdir dir_name` | Create a directory |
| `mkdir dir1 dir2 dir3` | Create multiple directories |
| `mkdir -p parent/child` | Create nested directories |
| `rmdir dir_name` | Remove an empty directory |
| `rm -r dir_name` | Remove a directory recursively |
| `rm -rf dir_name` | Force remove a directory recursively ⚠️ |
| `ls -R` | List directories recursively |

---

## Examples

Rename a directory:

```bash
mv projects my_projects
```

Create one directory:

```bash
mkdir project
```

Create multiple directories:

```bash
mkdir dir1 dir2 dir3
```

Create nested directories:

```bash
mkdir -p backend/api/routes
```

View directory structure recursively:

```bash
ls -R
```

Remove an empty directory:

```bash
rmdir dir1
```

Remove a directory with files:

```bash
rm -r dir2
```

Force remove without confirmation:

```bash
rm -rf dir2
```

---

## Key Takeaways

- `mv` renames directories (and can also move them).
- `mkdir` creates directories.
- `mkdir -p` creates parent directories automatically.
- `rmdir` works **only on empty directories**.
- `rm -r` deletes directories and everything inside.
- `rm -rf` force deletes recursively without asking ⚠️.
- `ls -R` displays all subdirectories recursively.

---

## For Backend/DevOps ⭐⭐⭐⭐⭐

These commands are used constantly:

- Create project folders with `mkdir`.
- Rename project directories using `mv`.
- Remove build/cache folders using `rm -rf`.
- Delete empty folders with `rmdir`.
- Inspect project structure using `ls -R`.

> ⚠️ **Be extremely careful with `rm -rf`**, especially as `root`. One wrong path can permanently delete important files.