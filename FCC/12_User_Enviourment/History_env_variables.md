# HISTFILE

The **`HISTFILE`** environment variable specifies the file where the Bash command history is stored.

By default, it points to:

```text
~/.bash_history
```

---

## View the History File

```bash
echo $HISTFILE
```

Example output:

```text
/home/student/.bash_history
```

---

## View Command History

```bash
history
```

---

## Change the History File

```bash
export HISTFILE=~/my_history
```

This stores future command history in the specified file.

> **Note:** Bash writes your command history to the file when the shell exits. The default history file is `~/.bash_history`.

# Recalling Previous Commands

Bash provides several ways to recall previously executed commands.

| Key / Command | Usage |
|---------------|-------|
| **↑ / ↓ Arrow keys** | Browse through previously executed commands |
| **`!!`** | Execute the previous command again |
| **`Ctrl + R`** | Search command history interactively |

---

## Examples

Run the last command again:

```bash
!!
```

Search for a previous command:

```text
Press Ctrl + R
```

Then start typing part of the command:

```text
(reverse-i-search)`git':
```

Use **↑ / ↓** to navigate through your command history.

> **Tip:** `Ctrl + R` is one of the fastest ways to find and rerun old commands without scrolling through the entire history.