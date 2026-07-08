# PATH Variable

The **`PATH`** environment variable contains a list of directories where the shell searches for executable commands.

Directories are separated by a colon (`:`).

```text
/path1:/path2:/path3
```

> An empty entry (`::` or a leading `:`) represents the **current working directory**.

---

## View the PATH

```bash
echo $PATH
```

Example output:

```text
/usr/local/bin:/usr/bin:/bin
```

---

## Add a Directory to PATH

Append a new directory:

```bash
export PATH=$PATH:$HOME/bin
```

Or prepend it (search it first):

```bash
export PATH=$HOME/bin:$PATH
```

Verify:

```bash
echo $PATH
```

Example:

```text
/home/student/bin:/usr/local/bin:/usr/bin:/bin
```

---

## Check Your Current Shell

The **`SHELL`** variable stores the default shell for the current user.

```bash
echo $SHELL
```

Example output:

```text
/bin/bash
```

> **Note:** The shell uses the `PATH` variable to locate commands, while the `SHELL` variable tells you which shell program you're currently using.