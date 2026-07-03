# Absolute Path vs Relative Path

In Linux, there are **two ways to specify the location of a file or directory**.

---

# 1. Absolute Path

An **absolute path** always starts from the **root directory (`/`)**.

- Starts with `/`
- Gives the complete location
- Works from **anywhere** in the filesystem

Example:

```bash
cd /usr/bin
```

Example:

```text
/
├── home
├── usr
│   └── bin
└── etc
```

No matter where you currently are:

```text
/home/aryan
```

or

```text
/tmp
```

Running:

```bash
cd /usr/bin
```

will always take you to:

```text
/usr/bin
```

---

# 2. Relative Path

A **relative path** is based on **your current working directory**.

It **does not start with `/`**.

Example:

Current directory:

```text
/home/aryan
```

Command:

```bash
cd DSA
```

Result:

```text
/home/aryan/DSA
```

Another example:

Current directory:

```text
/home/aryan/projects/backend
```

Command:

```bash
cd ../frontend
```

Result:

```text
/home/aryan/projects/frontend
```

---

# Relative Path Shortcuts

| Shortcut | Meaning |
|----------|---------|
| `.` | Current directory |
| `..` | Parent directory |
| `~` | Home directory |

Examples:

```bash
cd .
```

Stay in the current directory.

```bash
cd ..
```

Move to the parent directory.

```bash
cd ~
```

Move to your home directory.

---

# Absolute vs Relative

Suppose your current directory is:

```text
/home/aryan
```

Go to `/usr/bin`

### Absolute Path

```bash
cd /usr/bin
```

Starts from `/`.

---

### Relative Path

```bash
cd ../../usr/bin
```

Explanation:

```text
/home/aryan
      │
      └── ..
          ↓
      /home
          │
          └── ..
              ↓
              /
              │
              └── usr
                    │
                    └── bin
```

Both commands reach the same destination.

---

# Multiple Slashes

Linux treats multiple `/` as a single `/`.

These are all equivalent:

```bash
cd /usr/bin
```

```bash
cd //usr//bin
```

```bash
cd ////usr////bin
```

Linux interprets all of them as:

```text
/usr/bin
```

---

# When to Use Which?

### Use Absolute Path

- Shell scripts
- Cron jobs
- Configuration files
- When you know the complete location

Example:

```bash
cp file.txt /home/aryan/Documents/
```

---

### Use Relative Path

- Everyday terminal usage
- Navigating projects
- Moving between nearby folders

Example:

```bash
cd ../backend
```

---

# Quick Comparison

| Absolute Path | Relative Path |
|---------------|---------------|
| Starts with `/` | Doesn't start with `/` |
| Begins from the root directory | Begins from the current directory |
| Works from anywhere | Depends on where you currently are |
| Longer but unambiguous | Shorter and convenient |

---

# Key Takeaways

- `/usr/bin` → Absolute path
- `../usr/bin` → Relative path
- `.` → Current directory
- `..` → Parent directory
- `~` → Home directory
- Multiple slashes (`////`) are treated as a single `/`.

⭐ **For Backend/DevOps:** You'll constantly use both. Absolute paths are common in configuration files and automation scripts, while relative paths are used daily when navigating projects in the terminal.