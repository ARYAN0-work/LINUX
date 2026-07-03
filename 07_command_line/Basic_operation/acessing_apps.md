# Accessing Directories

Linux provides several commands to move between directories quickly.

---

## Common Commands

| Command | Purpose |
|---------|---------|
| `pwd` | Show current directory |
| `cd` | Go to your home directory |
| `cd ~` | Go to your home directory |
| `cd ..` | Move to the parent directory |
| `cd -` | Go back to the previous directory |
| `cd ~/Desktop` | Go to the Desktop folder |

---

## Environment Variable

`$HOME` stores the path to your home directory.

Example:

```bash
echo $HOME
```

Output:

```text
/home/username
```

---

## Examples

Go to the Desktop:

```bash
cd ~/Desktop
```

Go back to the previous directory:

```bash
cd -
```

Show the current directory:

```bash
pwd
```

---

## Key Takeaway

- `pwd` → Show current location
- `cd` or `cd ~` → Home directory
- `cd ..` → Parent directory
- `cd -` → Previous directory
- `$HOME` → Stores your home directory path

---

**For Backend/DevOps:** ⭐⭐⭐⭐⭐

These are some of the most frequently used Linux commands. You'll use `pwd` and `cd` almost every day while navigating project folders, configuration files, logs, and servers.


##### commmands linux instructor teached 

# Accessing Directories

Linux provides several commands to navigate between directories.

---

## Common Commands

| Command | Purpose |
|---------|---------|
| `pwd` | Print the current working directory |
| `cd` | Go to your home directory (`$HOME`) |
| `cd ~` | Go to your home directory |
| `cd ..` | Move to the parent directory |
| `cd -` | Switch to the previous directory |
| `cd <directory>` | Move to a specific directory (e.g. `cd /tmp`) |

---

## Environment Variable

### `$HOME`

`$HOME` stores the path of your home directory.

Example:

```bash
echo $HOME
```

Output:

```text
/home/aryan
```

You can use it like:

```bash
cd $HOME
```

Equivalent commands:

```bash
cd
cd ~
cd $HOME
```

---

## Examples

### Check Current Directory

```bash
pwd
```

Output:

```text
/home/aryan
```

---

### Go to Home Directory

```bash
cd
```

or

```bash
cd ~
```

---

### Go to Parent Directory

```bash
cd ..
```

Example:

```text
/home/aryan
        ↓
cd ..
        ↓
/home
```

---

### Go Back to Previous Directory

```bash
cd -
```

Example:

```text
/home/aryan
        ↓
cd /tmp
        ↓
/tmp
        ↓
cd -
        ↓
/home/aryan
```

Typing `cd -` again switches back:

```text
/home/aryan
        ↓
cd -
        ↓
/tmp
```

---

### Go to a Specific Directory

```bash
cd /tmp
```

or

```bash
cd /home/aryan/DSA
```

---

## Navigation Flow

```text
/
│
├── home
│   └── aryan
│
├── tmp
├── etc
└── usr
```

Examples:

```bash
cd /tmp
cd /home/aryan
cd ..
cd -
```

---

## Key Takeaways

- `pwd` → Shows where you are.
- `cd` / `cd ~` → Go to your home directory.
- `cd ..` → Move one level up.
- `cd -` → Return to the previous directory.
- `$HOME` → Stores the path of your home directory.
- Use `cd <directory>` to move to any location.

⭐ **For Backend/DevOps:** `pwd`, `cd`, `cd ..`, `cd -`, and `cd ~` are commands you'll use every day.