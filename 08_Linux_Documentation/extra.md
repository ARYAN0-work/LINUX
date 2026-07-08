# Other Documentation Sources

Linux documentation is not limited to `man` pages and GNU Info.

Many applications and Linux distributions provide additional documentation from various sources.

---

## 1. Desktop Help System

Many Linux desktop environments include graphical help applications.

Examples:
- GNOME Help
- KDE Help Center

These provide:
- User guides
- Tutorials
- System configuration help

---

## 2. Package Documentation

Many installed packages include their own documentation.

Common location:

```text
/usr/share/doc/
```

This directory may contain:

- README files
- Installation guides
- Configuration examples
- Changelogs
- License information

Example:

```bash
ls /usr/share/doc
```

View a package's documentation:

```bash
cd /usr/share/doc/<package-name>
```

---

## 3. Online Resources

When local documentation is insufficient, use official online resources.

Examples include:

- Official project documentation
- Distribution documentation
- Community wikis
- Tutorials
- Forums

Examples:

- Ubuntu Documentation
- Arch Wiki
- Debian Documentation
- GNU Documentation

---

## When Should You Use Each Source?

| Source | Best Use |
|---------|----------|
| `man` | Quick command reference |
| `info` | Detailed GNU documentation |
| `--help` | Quick syntax |
| Desktop Help | GUI-related help |
| Package Documentation | Software-specific information |
| Online Resources | Latest guides and tutorials |

---

# Summary

Linux provides documentation from many places:

- `man` pages
- GNU Info
- Command help (`--help`)
- Desktop help systems
- Package documentation (`/usr/share/doc/`)
- Official online resources

A good Linux user knows **where to look for information**, not just how to memorize commands.