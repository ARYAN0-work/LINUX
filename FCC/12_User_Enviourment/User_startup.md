# User Startup Files

Linux uses startup files to automatically configure the shell environment whenever a user logs in or starts a new shell.

## Global Startup Files

Global configuration files are stored in the `/etc` directory.

- Affect **all users** on the system.
- Managed by the system administrator.
- Used for system-wide environment variables, aliases, and shell settings.

---

## User Startup Files

User-specific configuration files are stored in the user's **home directory** (`/home/username`).

- Affect **only the current user**.
- Can add or override global settings.
- Commonly used for personal aliases, environment variables, and shell customization.

---

## How It Works

```text
        /etc
          │
          ▼
       +-------+
       | SHELL |
       +-------+
          ▲
          │
     /home/user

          │
          ▼
      TERMINAL
```

- When a terminal session starts, the **shell** reads configuration files.
- It first loads **global settings** from `/etc`.
- It then loads **user-specific settings** from the user's home directory.
- User configuration files can **override** global settings.

> **Note:** This layered configuration allows administrators to define default behavior while letting individual users customize their own shell environment.