# PS1 Command Line Prompt

The **`PS1`** environment variable defines how the Bash command prompt appears.

It supports special escape sequences to display useful information.

| Escape Sequence | Description |
|----------------|-------------|
| `\u` | Username |
| `\h` | Hostname |
| `\w` | Current working directory |
| `\!` | History number of the current command |
| `\d` | Current date |

### Example

```bash
export PS1="\u@\h:\w$ "
```

Output:

```text
student@ubuntu:~/projects$
```

> **Note:** Customize `PS1` in `~/.bashrc` to make your prompt permanent.