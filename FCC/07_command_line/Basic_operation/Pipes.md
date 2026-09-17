# Pipes (`|`)

A **pipe (`|`)** sends the output (`stdout`) of one command directly as the input (`stdin`) of another command.

```
Command 1 → Pipe → Command 2 → Pipe → Command 3
```

Instead of saving output to a file, the next command processes it immediately.

---

# Common Commands

### Basic Pipe

```bash
command1 | command2
```

Example:

```bash
ls | less
```

Display `ls` output page by page.

---

### Chain Multiple Commands

```bash
command1 | command2 | command3
```

Example:

```bash
cat file.txt | grep "error" | sort
```

---

### Count Lines

```bash
cat file.txt | wc -l
```

Count the number of lines.

---

### Search Text

```bash
cat file.txt | grep "hello"
```

Find lines containing `"hello"`.

---

### Sort Output

```bash
cat names.txt | sort
```

Sort file contents alphabetically.

---

### Remove Duplicate Lines

```bash
cat names.txt | sort | uniq
```

---

### Count Files

```bash
ls | wc -l
```

Count the number of files/directories.

---

### View Long Output Page by Page

```bash
ps aux | less
```

---

## Key Takeaways

- `|` passes **stdout** of one command to **stdin** of another.
- Avoids creating temporary files.
- Multiple pipes can be chained together.
- Makes commands small and reusable.
- One of the most powerful Linux features.

---

## Common Pipe Examples

```bash
ls | less

cat file.txt | grep "error"

cat names.txt | sort

cat names.txt | sort | uniq

ps aux | grep node

history | grep docker

ls -l | wc -l
```

---

## For Backend/DevOps ⭐⭐⭐⭐⭐

Pipes are used **every day** for:

- Filtering logs
- Searching processes
- Docker debugging
- Kubernetes debugging
- CI/CD scripting
- Log analysis

Examples:

```bash
docker ps | grep nginx

kubectl get pods | grep api

cat app.log | grep ERROR

history | grep git

ps aux | grep node

journalctl | grep nginx
```

> 💡 Think of a pipe as connecting programs together like a pipeline:
>
> **Command A → Output → Pipe → Command B → Output → Pipe → Command C**
>
> Each command performs one small task, making Linux commands powerful and composable.