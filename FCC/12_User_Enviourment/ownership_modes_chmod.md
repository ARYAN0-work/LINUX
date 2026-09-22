# Ownership, Permissions & `chmod`

## Ownership Commands

| Command | Purpose |
|---------|---------|
| `chown` | Change the owner of a file or directory |
| `chgrp` | Change the group ownership |
| `chmod` | Change file permissions |

---

# Linux Permission Format

Example:

```text
drwxrwxrwx
```

Breakdown:

```text
d rwx rwx rwx
│ │   │   │
│ │   │   └── Others
│ │   └────── Group
│ └────────── Owner (User)
└──────────── File type (d = directory, - = file)
```

Permission letters:

- `r` → Read
- `w` → Write
- `x` → Execute

---

# Changing Permissions with `chmod`

Example:

```bash
ls -l somefile
chmod uo+x,g-w somefile
ls -l somefile
```

Permission symbols:

- `+` → Add permission
- `-` → Remove permission
- `=` → Set exact permission

User classes:

- `u` → User (Owner)
- `g` → Group
- `o` → Others
- `a` → All

Example:

```bash
chmod u+x file
chmod g-w file
chmod o=r file
```

---

# Numeric Permission Values

| Permission | Value |
|------------|------:|
| Read (`r`) | 4 |
| Write (`w`) | 2 |
| Execute (`x`) | 1 |

Add the values together:

| Number | Permission |
|-------:|------------|
| 0 | `---` |
| 1 | `--x` |
| 2 | `-w-` |
| 3 | `-wx` |
| 4 | `r--` |
| 5 | `r-x` |
| 6 | `rw-` |
| 7 | `rwx` |

Example:

```bash
chmod 755 file
```

Means:

- Owner → `7` = `rwx`
- Group → `5` = `r-x`
- Others → `5` = `r-x`

```text
rwx r-x r-x
```

> **Tip:** `755` and `644` are the two most commonly used permission modes in Linux.