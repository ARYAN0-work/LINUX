# `paste` Command

Merges lines from multiple files side by side using a delimiter (default: tab).

## Syntax

```bash
paste <file1> <file2>
```

## Common Usage

| Command | Description |
|---------|-------------|
| `paste file1 file2` | Merge two files column by column. |
| `paste -d "," file1 file2` | Use `,` as the delimiter instead of a tab. |
| `paste -s file` | Merge all lines of a file into a single line. |
| `paste -s -d ":" file` | Merge all lines into one line using `:` as the delimiter. |