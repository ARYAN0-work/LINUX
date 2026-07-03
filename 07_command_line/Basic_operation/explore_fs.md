# Exploring the Linux Filesystem

Linux provides several commands to explore directories and view their contents.

---

# Common Commands

| Command | Purpose |
|---------|---------|
| `cd /` | Move to the root (`/`) directory |
| `cd <directory>` | Move to a specific directory |
| `ls` | List files and directories |
| `ls -a` | Show all files, including hidden files |
| `tree` | Display the directory structure as a tree |

---

# 1. `cd /`

Moves you to the root directory.

```bash
cd /
```

Output:

```text
/
```

Verify:

```bash
pwd
```

Output:

```text
/
```

---

# 2. `ls`

Lists the contents of the current directory.

Example:

```bash
ls
```

Output:

```text
Documents
Downloads
Pictures
Music
Desktop
```

Useful when you want to see what's inside a folder.

---

# 3. `ls -a`

Shows **all files**, including hidden files.

Hidden files begin with a dot (`.`).

Example:

```bash
ls -a
```

Output:

```text
.
..
.bashrc
.profile
.gitconfig
Documents
Downloads
```

### Hidden Files

Files beginning with `.` are hidden by default.

Examples:

```text
.bashrc
.git
.profile
```

These usually contain configuration/settings.

---

# 4. `tree`

Displays folders in a tree-like structure.

Example:

```bash
tree
```

Output:

```text
.
├── Documents
├── Downloads
├── Pictures
│   ├── Vacation
│   └── Family
└── Music
```

This is much easier to understand than `ls` for large projects.

> **Note:** `tree` is not installed on every Linux system.

Install it (Ubuntu/Debian):

```bash
sudo apt install tree
```

---

# Example Session

```bash
cd /
```

```bash
ls
```

Output:

```text
bin
boot
dev
etc
home
opt
tmp
usr
var
```

Show hidden files:

```bash
ls -a
```

Display the directory tree:

```bash
tree
```

---

# Difference Between `ls` and `tree`

| `ls` | `tree` |
|------|--------|
| Lists only the current directory | Shows the complete directory hierarchy |
| Faster | Easier to visualize folders |
| Built into every Linux system | May need installation |

---

# Key Takeaways

- `cd /` → Go to the root directory.
- `ls` → List files and folders.
- `ls -a` → Show hidden files (starting with `.`).
- `tree` → Display folders as a tree structure.
- Hidden files are mostly configuration files.

---

## For Backend/DevOps ⭐⭐⭐⭐⭐

You'll use these commands constantly:

- `cd` → Navigate between project folders.
- `ls` → Check files before running commands.
- `ls -a` → View `.git`, `.env`, `.dockerignore`, `.github`, etc.
- `tree` → Understand unfamiliar project structures quickly.

### commands linux instructor taught 

# Tree Command

The `tree` command displays files and directories in a **tree-like hierarchy**, making it much easier to visualize the filesystem than `ls`.

---

# Syntax

```bash
tree
```

---

# Basic Example

```bash
tree
```

Output:

```text
.
├── Documents
│   ├── Notes
│   └── Projects
├── Downloads
├── Music
└── Pictures

4 directories, 0 files
```

---

# If `tree` is Not Installed

Many Linux distributions don't install `tree` by default.

Install it on Ubuntu/Debian:

```bash
sudo apt update
```

```bash
sudo apt install tree
```

Verify installation:

```bash
tree --version
```

---

# `tree -d`

Display **directories only**.

```bash
tree -d
```

Example Output:

```text
.
├── Documents
├── Downloads
├── Music
└── Pictures
```

Files are hidden.

---

# Useful Options

### Show Hidden Files

```bash
tree -a
```

Displays hidden files such as:

```text
.bashrc
.git
.profile
```

---

### Show Directories Only

```bash
tree -d
```

---

### Limit the Depth

Show only two levels.

```bash
tree -L 2
```

Output:

```text
.
├── Documents
│   ├── Notes
│   └── Projects
├── Downloads
└── Pictures
```

---

### Show File Permissions

```bash
tree -p
```

Example:

```text
-rw-r--r--
drwxr-xr-x
```

---

### Show File Sizes

```bash
tree -s
```

Example:

```text
4.0K  README.md
8.0K  notes.txt
```

---

### Display Everything

```bash
tree -a
```

Shows:

- Hidden files
- Hidden directories
- Normal files
- Normal directories

---

# Difference Between `ls` and `tree`

## `ls`

```bash
ls
```

Output:

```text
Documents
Downloads
Pictures
Music
```

Only lists items in the current directory.

---

## `tree`

```bash
tree
```

Output:

```text
.
├── Documents
│   ├── Notes
│   └── Projects
├── Downloads
├── Music
└── Pictures
```

Shows the complete folder hierarchy.

---

# Common Error

```bash
tree
```

Output:

```text
Command 'tree' not found
```

Install it:

```bash
sudo apt install tree
```

---

# Key Takeaways

- `tree` → Display folders in a tree structure.
- `tree -d` → Show directories only.
- `tree -a` → Include hidden files.
- `tree -L <n>` → Limit tree depth.
- `tree -p` → Show permissions.
- `tree -s` → Show file sizes.
- Install with:

```bash
sudo apt install tree
```

---

## For Backend/DevOps ⭐⭐⭐⭐⭐

You'll use `tree` frequently to:

- Understand unfamiliar project structures.
- Visualize large repositories.
- Check folder organization.
- Document project layouts in README files.

Example:

```text
project/
├── src/
├── public/
├── node_modules/
├── package.json
└── README.md
```

It's one of the quickest ways to understand how a project is organized.