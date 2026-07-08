# `tail` Command

Displays the last few lines of a file.

## Syntax

```bash
tail -n <number> <filename>
```

### Example

```bash
tail -n 15 somefile.log
```

Displays the last 15 lines of `somefile.log`.

## Common Usage

| Command | Description |
|---------|-------------|
| `tail file` | Display the last 10 lines (default). |
| `tail -n 15 file` | Display the last 15 lines. |
| `tail -15 file` | Display the last 15 lines (short form). |
| `tail -f file` | Follow the file and display new lines as they are added (useful for log files). |
| `tail -c 100 file` | Display the last 100 bytes of a file. |