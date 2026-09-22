# Regular Expressions & Search Patterns

Regular expressions (regex) are patterns used to search and match text.

## Common Regex Patterns

| Pattern | Matches |
|---------|---------|
| `a..` | `azy` (an `a` followed by any 2 characters) |
| `b.|j.` | `br` or `ju` |
| `..$` | Ends with any 2 characters (e.g., `og`) |
| `l.*` | `lazy dog` |
| `l.*y` | `lazy` |
| `the.*` | The whole sentence starting with `the` |

## `grep` Command

Searches for text matching a pattern in files.

### Syntax

```bash
grep [OPTIONS] <pattern> <file>
```

### Common Usage

| Command | Description |
|---------|-------------|
| `grep "<pattern>" <file>` | Print all lines matching the pattern. |
| `grep -v "<pattern>" <file>` | Print lines that do **not** match the pattern. |
| `grep "[0-9]" <file>` | Print lines containing any digit (0–9). |
| `grep -C 3 "<pattern>" <file>` | Show 3 lines before and after each match. |