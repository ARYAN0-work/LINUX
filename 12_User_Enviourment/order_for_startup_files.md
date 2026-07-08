# Order of Startup Files

When a **login shell** starts, Bash looks for startup files in a specific order. It stops searching as soon as it finds the first existing file from the list below.

## Search Order

1. `~/.bash_profile`
2. `~/.bash_login`
3. `~/.profile`

> **Important:** Bash executes **only the first file it finds**. If `~/.bash_profile` exists, it will not read `~/.bash_login` or `~/.profile`.

---

## Startup File Priority

```text
1. ~/.bash_profile
        │
        ▼
   Exists?
   ├── Yes → Execute it → Stop
   └── No
        │
        ▼
2. ~/.bash_login
        │
        ▼
   Exists?
   ├── Yes → Execute it → Stop
   └── No
        │
        ▼
3. ~/.profile
        │
        ▼
   Exists?
   ├── Yes → Execute it
   └── No → Continue without a user login startup file
```

---

## What About `.bashrc`?

The `.bashrc` file is used for **interactive non-login shells**.

- Opening a new terminal window usually reads `~/.bashrc`.
- Logging in through a text console or SSH reads one of the login startup files (`.bash_profile`, `.bash_login`, or `.profile`).

To ensure the same settings are available everywhere, most Linux distributions include the following line inside `~/.bash_profile`:

```bash
if [ -f ~/.bashrc ]; then
    . ~/.bashrc
fi
```

This tells Bash to execute `.bashrc` after loading `.bash_profile`.

---

## Complete Flow

```text
             Login Shell?
                  │
        ┌─────────┴─────────┐
        │                   │
       Yes                  No
        │                   │
        ▼                   ▼
 ~/.bash_profile        ~/.bashrc
        │
        ▼
(Not found?)
        │
        ▼
 ~/.bash_login
        │
        ▼
(Not found?)
        │
        ▼
   ~/.profile
```

> **Note:** Most modern Linux distributions primarily use **`~/.bash_profile`** (which usually sources **`~/.bashrc`**) or simply **`~/.profile`**, depending on the distribution and shell configuration.