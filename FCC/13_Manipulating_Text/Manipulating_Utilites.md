# `sort` Command

Sorts lines in a file alphabetically or numerically.

## Syntax

```bash
sort <filename>
```

## Common Usage

| Command | Description |
|---------|-------------|
| `sort file` | Sort lines in ascending order. |
| `cat file1 file2 \| sort` | Combine two files, then sort the output. |
| `sort -r file` | Sort lines in reverse order. |
| `sort -k 3 file` | Sort lines based on the 3rd field (column). |