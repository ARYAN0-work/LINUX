# `sed` Command

Stream editor used to search, replace, and edit text.

## Syntax

```bash
sed -e <command> <filename>
```

### Common Usage

| Command | Description |
|---------|-------------|
| `sed -e 's/old/new/' file` | Replace the first occurrence of `old` with `new` in each line. |
| `sed -e 's/old/new/g' file` | Replace all occurrences in each line. |
| `sed -e '1,3s/old/new/g' file` | Replace in lines 1–3 only. |
| `sed -i 's/old/new/g' file` | Edit the file in place. |
| `sed -f script.sed file` | Execute commands from a script file. |
| `echo "I hate you" \| sed 's/hate/love/'` | Replace text from standard input. |

## Output to a New File

```bash
sed -e '1,2s/is/are/g' infile.txt > outfile.txt
```

Creates `outfile.txt` with the modified content while leaving `infile.txt` unchanged.


# `awk` Command

Powerful text-processing tool used to extract, filter, and format data.

## Syntax

```bash
awk 'program' <filename>
```

## Common Usage

| Command | Description |
|---------|-------------|
| `awk '{ print $0 }' /etc/passwd` | Print the entire file. |
| `awk -F: '{ print $1 }' /etc/passwd` | Print the first field (column) using `:` as the delimiter. |
| `awk -F: '{ print $1, $7 }' /etc/passwd` | Print the first and seventh fields of each line. |