# Standard File Streams & Redirection

Every Linux program uses three standard streams.

| Stream | Symbolic Name | File Descriptor | Default |
|---------|---------------|-----------------|----------|
| Standard Input | `stdin` | `0` | Keyboard |
| Standard Output | `stdout` | `1` | Terminal |
| Standard Error | `stderr` | `2` | Terminal |

---

# Common Commands

### Read input from a file

```bash
command < input.txt
```

Example:

```bash
sort < names.txt
```

---

### Redirect output to a file

```bash
command > output.txt
```

Example:

```bash
ls > files.txt
```

---

### Append output instead of overwriting

```bash
command >> output.txt
```

Example:

```bash
echo "Hello" >> log.txt
```

---

### Redirect errors only

```bash
command 2> error.txt
```

Example:

```bash
ls unknown_folder 2> errors.txt
```

---

### Append errors

```bash
command 2>> error.txt
```

---

### Redirect both output and errors (Bash)

```bash
command >& output.txt
```

or the more common modern syntax:

```bash
command > output.txt 2>&1
```

---

## Key Takeaways

- `stdin` → File descriptor **0**
- `stdout` → File descriptor **1**
- `stderr` → File descriptor **2**
- `<` takes input from a file.
- `>` writes output to a file (overwrites).
- `>>` appends output.
- `2>` redirects only errors.
- `2>>` appends errors.
- `>&` or `> file 2>&1` saves both output and errors together.

---

## For Backend/DevOps ⭐⭐⭐⭐⭐

These are used constantly for:

- Saving logs
- Capturing errors
- Feeding input to scripts
- Debugging applications
- Automation scripts
- CI/CD pipelines

Examples:

```bash
npm start > app.log 2>&1

python script.py > output.log

docker logs container > logs.txt

./backup.sh > backup.log 2> backup-error.log
```