# Wildcards (Pattern Matching)

Wildcards are special characters used to match filenames and directories without typing the full name.

They are commonly used with commands like:

- `ls`
- `cp`
- `mv`
- `rm`
- `find`
- `du`

---

# Why Use Wildcards?

Instead of typing long filenames, you can match them using patterns.

Example:

Instead of

```bash
ls report1.txt report2.txt report3.txt
```

you can write

```bash
ls report*
```

---

# Wildcard Characters

| Wildcard | Meaning |
|----------|---------|
| `*` | Matches zero or more characters |
| `?` | Matches exactly one character |
| `[set]` | Matches any one character inside the set |
| `[!set]` | Matches any character NOT in the set |

---

# 1. `*` (Asterisk)

Matches any number of characters.

### Example

```bash
ls *.out
```

Matches

```text
a.out
main.out
program.out
test.out
```

---

Another example

```bash
ls *.log
```

Matches

```text
system.log
error.log
auth.log
```

---

Beginning match

```bash
ls report*
```

Matches

```text
report.txt
report.pdf
report1.doc
```

---

Middle match

```bash
ls file*2025*
```

Matches

```text
file_backup_2025.txt
file2025.log
```

---

# 2. `?`

Matches exactly ONE character.

Example

```bash
ls file?.txt
```

Matches

```text
file1.txt
file2.txt
fileA.txt
```

Does NOT match

```text
file10.txt
file.txt
```

---

# 3. `[set]`

Matches one character from a set.

Example

```bash
ls file[123].txt
```

Matches

```text
file1.txt
file2.txt
file3.txt
```

---

Example

```bash
ls log[a-c].txt
```

Matches

```text
loga.txt
logb.txt
logc.txt
```

---

# 4. `[!set]`

Matches anything NOT inside the brackets.

Example

```bash
ls file[!123].txt
```

Matches

```text
fileA.txt
fileX.txt
```

Does NOT match

```text
file1.txt
file2.txt
file3.txt
```

---

# Real Examples

### List all log files

```bash
ls *.log
```

---

### Find all shell scripts

```bash
ls *.sh
```

---

### List every text file

```bash
ls *.txt
```

---

### Files beginning with "app"

```bash
ls app*
```

---

### Files ending with ".conf"

```bash
ls *.conf
```

---

### Files with exactly one unknown character

```bash
ls file?.txt
```

---

### List only JPG images

```bash
ls *.jpg
```

---

### Remove every temporary file

```bash
rm *.tmp
```

---

### Copy every PDF

```bash
cp *.pdf backup/
```

---

### Move every log

```bash
mv *.log logs/
```

---

# Wildcards with Other Commands

## `du`

```bash
du -sh *.log
```

Shows the size of every `.log` file.

---

## `cp`

```bash
cp *.txt backup/
```

Copies all text files.

---

## `mv`

```bash
mv *.jpg images/
```

Moves every JPG image.

---

## `rm`

```bash
rm *.tmp
```

Deletes all temporary files.

⚠️ Be careful with `rm` and wildcards.

---

## `cat`

```bash
cat *.txt
```

Displays all text files one after another.

---

# Wildcards vs Regular Expressions

Wildcards are **not** regular expressions.

For example,

```bash
sudo apt install "vmware*"
```

does **not** install every package starting with `vmware`.

The shell passes the quoted string directly to `apt`, and `apt` treats it as a package name/pattern according to its own rules. Wildcards are primarily expanded by the shell when matching **filenames**, not arbitrary text.

---

# Common Commands Using Wildcards

```bash
ls *.txt

cp *.pdf backup/

mv *.jpg images/

rm *.tmp

cat *.log

du -sh *.log
```

---

# Key Points

- `*` → zero or more characters
- `?` → exactly one character
- `[abc]` → one character from the set
- `[!abc]` → one character NOT in the set
- Wildcards are mainly expanded by the **shell** for matching filenames.

---

# For Backend/DevOps ⭐⭐⭐⭐⭐

You'll frequently use wildcards for:

- Cleaning log files

```bash
rm *.log
```

- Viewing logs

```bash
cat *.log
```

- Copying configuration files

```bash
cp *.conf backup/
```

- Finding shell scripts

```bash
ls *.sh
```

- Viewing certificate files

```bash
ls *.pem
```

- Checking disk usage

```bash
du -sh *.log
```

> 💡 **Remember:** Wildcards let the **shell** expand filename patterns before the command runs, making it easy to work with many files at once.