# Soft (Symbolic) Links in Linux

A **soft link (symbolic link or symlink)** is a special file that **stores the path to another file**.

Unlike a hard link, a soft link **does not point directly to the file's inode**.

Think of it like a **shortcut** on Windows.

```
file3 (shortcut)
      │
      ▼
file1
      │
      ▼
   Actual Data
```

---

# Creating a Soft Link

Create a file:

```bash
touch file1
```

Create a symbolic link:

```bash
ln -s file1 file3
```

Syntax:

```bash
ln -s <target_file> <symbolic_link_name>
```

---

# Checking Symbolic Links

Use:

```bash
ls -li file1 file3
```

Example:

```bash
touch file1
ln -s file1 file3
ls -li file1 file3
```

Output:

```text
38809 -rw-r--r-- 1 aryan aryan 0 Jan 6 09:18 file1
38810 lrwxrwxrwx 1 aryan aryan 5 Jan 6 09:22 file3 -> file1
```

Notice:

- `file1` and `file3` have **different inode numbers**.
- `l` at the beginning means **symbolic link**.
- `file3 -> file1` means `file3` points to `file1`.

---

# Reading Through a Soft Link

Create some data:

```bash
echo "Hello Linux" > file1
```

Read through the link:

```bash
cat file3
```

Output:

```text
Hello Linux
```

The soft link redirects Linux to the original file.

---

# What Happens If the Original File Is Deleted?

Delete the original:

```bash
rm file1
```

Now try:

```bash
cat file3
```

Output:

```text
cat: file3: No such file or directory
```

The link still exists, but it points to a file that no longer exists.

This is called a **broken (dangling) symbolic link**.

---

# Why Use Symbolic Links?

Symbolic links are useful because they:

- Work across different filesystems.
- Can link directories.
- Act like shortcuts.
- Save disk space.

Example:

```bash
ln -s /var/log logs
```

Now you can access logs using:

```bash
cd logs
```

instead of typing:

```bash
cd /var/log
```

---

# Hard Link vs Soft Link

| Hard Link | Soft Link |
|------------|-----------|
| Same inode | Different inode |
| Points directly to data | Points to file path |
| Survives if original filename is deleted | Breaks if original file is deleted |
| Cannot cross filesystems | Can cross filesystems |
| Cannot link directories | Can link directories |
| Created with `ln` | Created with `ln -s` |

---

# Visual Comparison

### Hard Link

```
file1 ─┐
        ├──► inode ───► Data
file2 ─┘
```

Both names share the **same inode**.

---

### Soft Link

```
file3
  │
  ▼
file1
  │
  ▼
inode
  │
  ▼
Data
```

The symlink points to the **filename/path**, not the inode.

---

# Common Commands

Create a file:

```bash
touch file1
```

Create a symbolic link:

```bash
ln -s file1 file3
```

View links:

```bash
ls -li
```

Read through the link:

```bash
cat file3
```

Delete original:

```bash
rm file1
```

Delete only the symlink:

```bash
rm file3
```

---

# Key Takeaways

- A **soft link** is like a Windows shortcut.
- Created using `ln -s`.
- Has its **own inode**.
- Stores the **path** to another file.
- Can link directories.
- Can cross different filesystems.
- Breaks if the original file is deleted.

---

## For Backend/DevOps ⭐⭐⭐⭐⭐

You'll encounter symbolic links frequently when working with Linux servers.

Examples:

- `/bin -> /usr/bin`
- `/lib -> /usr/lib`
- `/etc/nginx/sites-enabled` uses symlinks.
- Docker, Kubernetes, Node.js, and many Linux tools rely on symbolic links.

Knowing how to inspect (`ls -l`) and create (`ln -s`) symlinks is a practical Linux skill.