# `strings` Command

Extracts readable text strings from binary files.

## Syntax

```bash
strings [OPTIONS] <file>
```

## Common Usage

| Command | Description |
|---------|-------------|
| `strings book1.xls` | Display all readable strings from a binary file. |
| `strings book1.xls \| grep "text"` | Search for a specific string inside the extracted output. |

---

# `tr` Command

Translates, deletes, or squeezes characters from input.

## Syntax

```bash
tr [OPTIONS] <set1> [set2]
```

## Common Usage

| Command | Description |
|---------|-------------|
| `tr abcdefghijklmnopqrstuvwxyz ABCDEFGHIJKLMNOPQRSTUVWXYZ` | Convert lowercase to uppercase. |
| `tr '{}' '()' < input.txt > output.txt` | Replace `{}` with `()`. |
| `echo "This is text" \| tr '[:space:]' '\t'` | Convert spaces to tabs. |
| `echo "This   is   text" \| tr -s '[:space:]'` | Squeeze repeated spaces into one. |
| `echo "the geek stuff" \| tr -d 't'` | Delete all `t` characters. |
| `echo "id 432234" \| tr -cd '[:digit:]'` | Keep only digits. |
| `tr -cd '[:print:]' < file.txt` | Remove non-printable characters. |
| `tr -s '\n' ' ' < file.txt` | Join all lines into a single line. |