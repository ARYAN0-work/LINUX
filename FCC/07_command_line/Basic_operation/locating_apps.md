# Locating Applications

Linux stores executable programs in specific directories.

---

## Common Locations

| Directory | Purpose |
|-----------|---------|
| `/bin` | Essential user commands |
| `/usr/bin` | Most installed user applications |
| `/sbin` | Essential system administration commands |
| `/usr/sbin` | System administration programs |
| `/opt` | Optional third-party software |
| `/usr/local/bin` | User-installed programs |
| `/usr/local/sbin` | User-installed system programs |
| `~/bin` | User's personal executables |

---

## Finding an Application

Use the `which` command to find where a command is located.

```bash
which diff
```

Example output:

```text
/usr/bin/diff
```

Another example:

```bash
which git
```

Output:

```text 
/usr/bin/git
```

---

## Key Takeaway

- `/bin` → Essential commands
- `/usr/bin` → Most applications
- `/sbin` & `/usr/sbin` → System administration tools
- `/opt` → Third-party software
- `/usr/local/bin` → Manually installed programs
- `~/bin` → Personal executables
- Use `which <command>` to locate an executable.

For Backend/DevOps: ⭐⭐⭐⭐⭐
Remember which well—you'll use it frequently while debugging PATH issues and locating installed tools like node, docker, git, python, nginx, etc.