# `tee` Command

Displays command output on the terminal and saves it to a file.

## Syntax

```bash
tee [OPTIONS] <file>
```

## Common Usage

| Command | Description |
|---------|-------------|
| `ls -l \| tee newfile` | Display output and save it to `newfile`. |
| `command \| tee file1 file2` | Save output to multiple files. |
| `command \| tee -a file` | Append output instead of overwriting. |

---

# `wc` Options

Common options used with the `wc` (word count) command.

| Option | Description |
|--------|-------------|
| `-l` | Display the number of lines. |
| `-c` | Display the number of bytes. |
| `-w` | Display the number of words. |

---

# `cut` Command

Extracts specific fields or columns from text.

## Syntax

```bash
cut [OPTIONS] <file>
```

## Common Usage

| Command | Description |
|---------|-------------|
| `ls -l \| cut -d " " -f3` | Extract the 3rd field using space as the delimiter. |
| `cut -d ":" -f1 /etc/passwd` | Extract the first field using `:` as the delimiter. |
| `cut -c 1-5 file.txt` | Extract characters 1–5 from each line. |