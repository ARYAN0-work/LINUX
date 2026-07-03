# Hard Links in Linux

A **hard link** is another filename that points to the **same file (same inode)** on the disk.

Think of it like giving **one person two different names**.

```
File Data
    ▲
    │
┌───┴────┐
│        │
file1  file2
```

Both names refer to the **same physical data**.

---

# Creating a Hard Link

Create a file:

```bash
touch file1
```

Create a hard link:

```bash
ln file1 file2
```

Syntax:

```bash
ln <existing_file> <new_hard_link>
```

---

# Checking Hard Links

Use:

```bash
ls -li
```

Example:

```bash
touch file1
ln file1 file2
ls -li
```

Output:

```text
38809 -rw-r--r-- 2 aryan aryan 0 Jan 6 09:18 file1
38809 -rw-r--r-- 2 aryan aryan 0 Jan 6 09:18 file2
```

Notice:

- Same inode number (`38809`)
- Link count is `2`

This means both names point to the **same file**.

---

# What is an Inode?

Every file in Linux has a unique **inode**.

The inode stores:

- File permissions
- Owner
- Size
- Creation time
- Location of data on disk

The filename itself is **not** stored in the inode.

Instead:

```text
file1
   │
   ▼
inode 38809
   ▲
   │
file2
```

Both names point to the same inode.

---

# Editing a Hard Link

Create:

```bash
echo "Hello" > file1
```

Read from file2:

```bash
cat file2
```

Output:

```text
Hello
```

Why?

Because `file1` and `file2` are actually the **same file**.

---

# Deleting One Hard Link

Delete:

```bash
rm file1
```

Now check:

```bash
cat file2
```

Output:

```text
Hello
```

The data is **still there** because `file2` still points to the inode.

---

# When Does the File Actually Get Deleted?

Only when **all hard links are removed**.

Example:

```bash
rm file1
```

File still exists.

```bash
rm file2
```

Now the inode has **zero links**, so Linux deletes the actual file.

---

# Viewing Link Count

```bash
ls -l
```

Example:

```text
-rw-r--r-- 2 aryan aryan 20 file1
```

The number:

```text
2
```

means there are **two hard links** to the same inode.

---

# Limitations of Hard Links

❌ Cannot link directories (normally).

❌ Cannot span different filesystems or partitions.

✔ Can only link regular files on the same filesystem.

---

# Hard Link vs Copy

Hard Link:

```bash
ln file1 file2
```

Copy:

```bash
cp file1 file2
```

Hard link:

```
file1 ─┐
        ├──► inode
file2 ─┘
```

Copy:

```
file1 ─► inode A

file2 ─► inode B
```

A copy creates a completely separate file.

---

# Hard Link vs Symbolic Link

| Hard Link | Symbolic Link |
|------------|---------------|
| Same inode | Different inode |
| Points directly to data | Points to filename/path |
| Works if original filename is deleted | Breaks if original file is deleted |
| Cannot cross filesystems | Can cross filesystems |
| Cannot link directories | Can link directories |

(Symbolic links are covered in the next section.)

---

# Common Commands

Create a file:

```bash
touch file1
```

Create a hard link:

```bash
ln file1 file2
```

Show inode numbers:

```bash
ls -li
```

Delete a link:

```bash
rm file1
```

Read file:

```bash
cat file2
```

---

# Key Takeaways

- A hard link is another name for the **same file**.
- Multiple hard links share the **same inode**.
- `ln` creates a hard link.
- `ls -li` shows inode numbers.
- The file is deleted only when **all hard links are removed**.
- Hard links cannot cross filesystems or link directories.

---

## For Backend/DevOps ⭐⭐⭐⭐☆

You won't create hard links every day, but understanding them helps when:

- Learning how Linux filesystems work.
- Understanding inode behavior.
- Managing backups and storage efficiently.
- Debugging filesystem-related issues.