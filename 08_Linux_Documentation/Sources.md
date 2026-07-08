# Documentation Sources

Linux provides multiple sources of documentation. Each source is useful in different situations.

---

## 1. Man Pages

**Purpose**
- The primary documentation system in Linux.
- Provides detailed information about commands and programs.

**Features**
- Command description
- Syntax
- Options
- Examples
- Related commands

**Example**

```bash
man ls
man cp
man mkdir
```

---

## 2. GNU Info

**Purpose**
- More detailed documentation than man pages.
- Organized as linked documents that can be navigated.

**Features**
- Hierarchical structure
- Cross references
- More explanations
- Better for learning complex software

**Example**

```bash
info ls
info bash
```

---

## 3. Command Help

Most commands include a built-in help option.

### Using `--help`

```bash
ls --help
cp --help
grep --help
```

### Shell Built-in Commands

Use:

```bash
help
```

Example:

```bash
help cd
help echo
```

---

## 4. Other Documentation Sources

Linux distributions also provide documentation through:

- `/usr/share/doc/`
- README files
- Official documentation websites
- Community wikis
- Tutorials
- Distribution documentation

Examples:

```text
/usr/share/doc/
```

---

# Which Source Should You Use?

| Documentation Source | Best For |
|----------------------|----------|
| `man` | Complete command reference |
| `info` | Detailed learning and navigation |
| `--help` | Quick syntax and options |
| `help` | Shell built-in commands |
| `/usr/share/doc/` | Package-specific documentation |

---

# Summary

Linux offers several ways to get help:

- **Man Pages** → Standard Linux documentation.
- **GNU Info** → Detailed manuals with navigation.
- **Command Help (`--help`)** → Quick command usage.
- **Shell Help (`help`)** → Help for built-in shell commands.
- **Other Documentation** → Package docs, official websites, and community resources.

A good Linux user doesn't memorize every command—they know where to find accurate documentation quickly.