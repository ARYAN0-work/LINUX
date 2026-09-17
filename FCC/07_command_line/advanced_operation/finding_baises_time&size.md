# Finding Files Based on Time & Size

The `find` command can search for files based on their **creation/change time**, **access time**, **modification time**, and **size**. This is useful for locating recently modified files, old backups, large files, or temporary files.

---

# Time-Based Search

## `-ctime`

Searches for files whose **metadata (inode) was changed** a specific number of days ago.

### Syntax

```bash
find [path] -ctime n
```

### Example

```bash
find / -ctime 3
```

Finds files whose metadata changed **exactly 3 days ago**.

---

## `-atime`

Searches for files based on **last access time** (days).

### Syntax

```bash
find [path] -atime n
```

### Example

```bash
find . -atime 7
```

Finds files last accessed **exactly 7 days ago**.

---

## `-mtime`

Searches for files based on **last modification time** (days).

### Syntax

```bash
find [path] -mtime n
```

### Example

```bash
find . -mtime 2
```

Finds files modified **exactly 2 days ago**.

---

# Minute-Based Search

Instead of days, `find` can search using **minutes**.

---

## `-cmin`

Searches by metadata change time in **minutes**.

### Example

```bash
find . -cmin 30
```

Files whose metadata changed **30 minutes ago**.

---

## `-amin`

Searches by last access time in **minutes**.

### Example

```bash
find . -amin 15
```

Files accessed **15 minutes ago**.

---

## `-mmin`

Searches by last modification time in **minutes**.

### Example

```bash
find . -mmin 60
```

Files modified **60 minutes ago**.

---

# Time Operators

The same operators work for all time options (`ctime`, `atime`, `mtime`, `cmin`, `amin`, `mmin`).

| Operator | Meaning |
|----------|---------|
| `n` | Exactly `n` days/minutes ago |
| `+n` | More than `n` days/minutes ago |
| `-n` | Less than `n` days/minutes ago |

### Examples

Modified within the last day:

```bash
find . -mtime -1
```

Modified more than 30 days ago:

```bash
find . -mtime +30
```

Accessed within the last 10 minutes:

```bash
find . -amin -10
```

Modified more than an hour ago:

```bash
find . -mmin +60
```

---

# Finding Files by Size

The `-size` option searches for files based on their size.

## Syntax

```bash
find [path] -size size
```

---

## Size Units

| Unit | Meaning |
|------|---------|
| `c` | Bytes |
| `k` | Kilobytes (KiB) |
| `M` | Megabytes (MiB) |
| `G` | Gigabytes (GiB) |

---

## Examples

Find files exactly 10 MB:

```bash
find . -size 10M
```

Find files larger than 100 MB:

```bash
find . -size +100M
```

Find files smaller than 5 MB:

```bash
find . -size -5M
```

Find files exactly 500 KB:

```bash
find . -size 500k
```

Find files larger than 1 GB:

```bash
find . -size +1G
```

---

# Combining Time and Size

Find large log files modified within the last day:

```bash
find . -name "*.log" -size +50M -mtime -1
```

Find files larger than 1 GB:

```bash
find / -type f -size +1G
```

Find text files modified within the last hour:

```bash
find . -type f -name "*.txt" -mmin -60
```

---

# Summary

- `-ctime` → Metadata changed (days)
- `-atime` → Last accessed (days)
- `-mtime` → Last modified (days)
- `-cmin` → Metadata changed (minutes)
- `-amin` → Last accessed (minutes)
- `-mmin` → Last modified (minutes)
- `-size` → Search by file size
- `+` means **greater than**
- `-` means **less than**
- No prefix means **exactly**

---

# Quick Reference

```bash
find / -ctime 3
find . -atime 7
find . -mtime 2

find . -cmin 30
find . -amin 15
find . -mmin 60

find . -mtime -1
find . -mtime +30
find . -amin -10
find . -mmin +60

find . -size 10M
find . -size +100M
find . -size -5M
find . -size +1G

find . -name "*.log" -size +50M -mtime -1
find / -type f -size +1G
find . -type f -name "*.txt" -mmin -60
```