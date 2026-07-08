# Creating and Applying Patch Files

A **patch file** contains only the differences between two versions of a file. Instead of sending the entire modified file, you can send the patch file, and the recipient can apply those changes to their original file.

This is widely used in:

- Open Source contributions
- Linux kernel development
- Git workflows
- Software maintenance

---

# Creating a Patch File

Use `diff` with the `-Nur` options.

## Syntax

```bash
diff -Nur originalfile newfile > patchfile
```

### Explanation

- `-N` → Treat absent files as empty.
- `-u` → Produce unified diff format (easy to read).
- `-r` → Compare directories recursively.
- `>` → Save the output into a patch file.

### Example

```bash
diff -Nur app_v1.c app_v2.c > app.patch
```

---

# Applying a Patch

There are two common ways to apply a patch.

## Method 1 (Most Common)

```bash
patch -p1 < patchfile
```

### Explanation

- `patch` → Applies the changes.
- `-p1` → Removes the first directory level from file paths inside the patch.
- `<` → Reads the patch from the specified file.

---

## Method 2

```bash
patch originalfile patchfile
```

This directly applies the patch to the specified original file.

---

# Workflow

```text
Original File
      │
      ▼
Modify File
      │
      ▼
diff -Nur original new > patchfile
      │
      ▼
Send patchfile
      │
      ▼
patch -p1 < patchfile
      │
      ▼
Updated File
```

---

# Why Use Patch Files?

Instead of sharing an entire file:

- Smaller file size
- Easier to review changes
- Preserves version history
- Common in Linux and Open Source projects

---

# Key Points

- A patch file stores only the differences between files.
- Create a patch using `diff -Nur`.
- Apply a patch using `patch`.
- `patch -p1 < patchfile` is the most commonly used command.
- Patch files are heavily used in Linux development and open-source contributions.