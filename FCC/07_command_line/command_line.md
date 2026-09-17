# Linux Command Structure

Almost every Linux command follows a simple structure:

```text
command [options] [arguments]
```

Example:

```bash
ls -a /home/angela
```

Here:

```text
┌─────────┬──────────┬────────────────┐
│ Command │ Options  │   Arguments    │
├─────────┼──────────┼────────────────┤
│ ls      │ -a       │ /home/angela   │
└─────────┴──────────┴────────────────┘
```

---

## 1. Command

The **command** specifies the program or action you want Linux to execute.

Examples:

```bash
ls
```

```bash
cat
```

```bash
mkdir
```

```bash
grep
```

---

## 2. Options (Flags)

**Options** modify the behavior of a command.

They usually begin with a hyphen (`-`) or double hyphen (`--`).

Examples:

```bash
ls -a
```

Shows hidden files.

```bash
ls -l
```

Displays files in long format.

```bash
ls -la
```

Combines both `-l` and `-a`.

Long option example:

```bash
ls --help
```

Displays the help page.

---

## 3. Arguments

An **argument** tells the command **what to operate on**.

It can be:

- A file
- A directory
- A username
- A process
- A package
- Any other input required by the command

Example:

```bash
cat notes.txt
```

Argument → `notes.txt`

Example:

```bash
mkdir projects
```

Argument → `projects`

Example:

```bash
rm file.txt
```

Argument → `file.txt`

---

## Complete Example

```bash
ls -la /home/angela
```

Breakdown:

| Part | Value | Meaning |
|------|-------|---------|
| Command | `ls` | List directory contents |
| Option | `-la` | Long format + show hidden files |
| Argument | `/home/angela` | Directory to list |

---

## Another Example

```bash
grep -i "hello" file.txt
```

| Part | Value |
|------|-------|
| Command | `grep` |
| Option | `-i` (case-insensitive search) |
| Arguments | `"hello"` and `file.txt` |

---

## 💡 Note for Backend & DevOps Developers

Understanding the **command → option → argument** pattern makes learning Linux much easier because almost every command follows this structure.

Once you know this pattern, you can quickly understand new commands just by reading their manual (`man`) or help page (`--help`).