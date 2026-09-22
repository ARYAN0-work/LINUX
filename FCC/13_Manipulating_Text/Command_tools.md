# `cat` Command

Displays the contents of a file.

## Syntax

```bash
cat <filename>
```

### Example

```bash
cat readme.txt
```

Displays the contents of `readme.txt`.

## Common Usage

| Command | Description |
|---------|-------------|
| `cat file1 file2` | Display contents of multiple files. |
| `cat file1 file2 > newfile` | Combine files into a new file. |
| `cat file >> existingfile` | Append a file to another file. |
| `cat > file` | Create a new file (press `Ctrl + D` to save). |
| `cat >> file` | Append text to an existing file (press `Ctrl + D` to save).|

# `tac` Command

Displays file contents in reverse order (last line to first).

## Syntax

```bash
tac <filename>
```

### Example

```bash
tac file
```

Displays the file from bottom to top.

## Common Usage

| Command | Description |
|---------|-------------|
| `tac file` | Display file contents in reverse order. |
| `tac file1 file2 > newfile` | Reverse and combine multiple files into a new file. |

## Here Document (Multi-line Input)

```bash
cat << EOF > file.txt
Line 1
Line 2
EOF
```

Creates `file.txt` with multiple lines until the `EOF` marker is reached.

# `head` Command

Displays the first few lines of a file.

## Syntax

```bash
head -n <number> <filename>
```

### Example

```bash
head -n 5 /etc/default/grub
```

Displays the first 5 lines of `/etc/default/grub`.

## Common Usage

| Command | Description |
|---------|-------------|
| `head file` | Display the first 10 lines (default). |
| `head -n 5 file` | Display the first 5 lines. |
| `head -15 file` | Display the first 15 lines (short form). |
| `head -c 100 file` | Display the first 100 bytes of a file. |