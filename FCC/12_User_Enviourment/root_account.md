# Root Account and `sudo`

The **root** account is the superuser in Linux. It has unrestricted access to the entire system and can perform administrative tasks.

## Root User

- Has full control over the system.
- Can access and modify any file.
- Can install software, manage users, and change system settings.

The **`#`** symbol in the terminal usually indicates you are logged in as the **root** user.

```text
root@linux:~#
```

---

## What is `sudo`?

`sudo` (**SuperUser DO**) allows a normal user to execute a command with root privileges.

Example:

```bash
sudo apt update
```

A popular joke explains it like this:

```text
User: Make me a sandwich.
Computer: Make it yourself.

User: sudo make me a sandwich.
Computer: Okay.
```

---

## Environment Variables

Display the value of an environment variable:

```bash
echo $HOME
echo $SHELL
```

Set a temporary variable:

```bash
export VARIABLE=value
```

Make it permanent by adding it to `~/.bashrc`:

```bash
export VARIABLE=value
```

Reload the file:

```bash
source ~/.bashrc
```

---

## Using `$HOME`

The `$HOME` environment variable stores the path to your home directory.

```bash
echo $HOME
```

Example:

```text
/home/student
```

You can use it to quickly return home:

```bash
cd $HOME
```

Example:

```bash
cd /usr/bin
pwd
# /usr/bin

cd $HOME
pwd
# /home/student
```

> **Note:** Environment variables (like `$HOME` and `$SHELL`) make commands more portable by avoiding hardcoded paths.