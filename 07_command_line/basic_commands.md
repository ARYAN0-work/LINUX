# Basic Linux Commands

These are some of the most commonly used Linux commands for viewing files and accessing documentation.

---

## 📄 `cat` — Display or Combine File Contents

The `cat` (concatenate) command is used to display the contents of one or more files. It can also combine multiple files into a single output.

### Syntax

```bash
cat <file_name>
```

### Example

```bash
cat notes.txt
```

### Common Uses

- Display the contents of a file.
- Combine multiple files.
- Create small text files using terminal input.

Example:

```bash
cat file1.txt file2.txt
```

---

## 📑 `head` — Display the First Lines of a File

The `head` command displays the beginning of a file.

By default, it shows the **first 10 lines**.

### Syntax

```bash
head <file_name>
```

### Example

```bash
head notes.txt
```

### Display First 5 Lines

```bash
head -5 notes.txt
```

### Common Uses

- Preview large files.
- Check log files.
- Verify file contents without opening the entire file.

---

## 📑 `tail` — Display the Last Lines of a File

The `tail` command displays the end of a file.

By default, it shows the **last 10 lines**.

### Syntax

```bash
tail <file_name>
```

### Example

```bash
tail notes.txt
```

### Display Last 20 Lines

```bash
tail -20 notes.txt
```

### Follow a Growing File (Useful for Logs)

```bash
tail -f server.log
```

This continuously displays new lines as they are added to the file.

### Common Uses

- Monitor log files.
- View recent output.
- Debug running applications.

---

## 📚 `man` — View Command Documentation

The `man` (manual) command opens the official documentation for Linux commands.

### Syntax

```bash
man <command>
```

### Example

```bash
man ls
```

```bash
man grep
```

```bash
man cat
```

### Navigation Inside `man`

| Key | Action |
|------|--------|
| ↑ / ↓ | Scroll line by line |
| Space | Next page |
| b | Previous page |
| /text | Search for text |
| n | Next search result |
| q | Quit the manual |

### Common Uses

- Learn command syntax.
- View available options.
- Understand command behavior.

---

## 💡 Note for Backend & DevOps Developers

These commands are used almost every day:

- `cat` → Quickly inspect configuration files.
- `head` → Preview the beginning of logs or datasets.
- `tail` → Monitor application and server logs in real time.
- `man` → Read official documentation directly from the terminal.

Mastering these basic commands will make working with Linux servers much faster and more efficient.