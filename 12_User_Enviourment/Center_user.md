# Center User

The `whoami` and `who` commands are useful for identifying users currently logged into a Linux system.

## Check the Current User

Print the username of the user executing the current shell.

```bash
whoami
```

**Example Output**

```text
student
```

---

## List Logged-in Users

Display all users currently logged into the system along with their terminal, login time, and remote host (if applicable).

```bash
who
```

**Example Output**

```text
student  :0      2021-06-04 05:51 (:0)
student  pts/2   2021-06-04 06:30 (192.168.235.1)
student  pts/3   2021-06-04 06:31 (127.0.0.1)
```

### Understanding the Output

- **Username** – Name of the logged-in user.
- **Terminal** – The terminal session (`:0`, `pts/2`, `pts/3`, etc.).
- **Login Time** – When the session started.
- **Remote Host** – The IP address or hostname from which the user connected.

> **Note:** Multiple entries for the same username indicate that the user has multiple active login sessions.