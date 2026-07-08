# User and Group IDs

Every process in Linux runs under a user account and a group.

These IDs determine **who owns the process** and **what permissions it has**.

---

# User IDs

## 1. Real User ID (RUID)

The **RUID** identifies the user who started the process.

### Purpose

- Identifies the process owner.
- Used for auditing and tracking who launched the process.

Example:

```text
User "aryan" starts Firefox.

RUID = aryan
```

---

## 2. Effective User ID (EUID)

The **EUID** determines the permissions the process currently has.

### Purpose

- Controls access to files and resources.
- Used when checking permissions.

Example:

```text
A program running with root privileges

EUID = root
```

---

# Group IDs

## 3. Real Group ID (RGID)

The **RGID** identifies the group that started the process.

### Purpose

- Identifies the owner's primary group.
- Used for ownership information.

Example:

```text
Group = developers
```

---

## 4. Effective Group ID (EGID)

The **EGID** determines the group permissions available to the process.

### Purpose

- Controls group-based access rights.
- Used during permission checks.

---

# Comparison

| ID | Meaning | Purpose |
|----|---------|---------|
| RUID | Real User ID | User who started the process |
| EUID | Effective User ID | Current user permissions |
| RGID | Real Group ID | Group that started the process |
| EGID | Effective Group ID | Current group permissions |

---

# Why Do We Need Real and Effective IDs?

Normally:

```text
RUID = EUID
RGID = EGID
```

However, some programs temporarily run with different privileges.

Example:

```text
User: aryan

RUID = aryan
EUID = root
```

This allows the program to perform privileged operations while still remembering who started it.

---

# Key Takeaways

- Every process has user and group identifiers.
- **RUID** identifies the user who launched the process.
- **EUID** determines what the process is allowed to do.
- **RGID** identifies the original group.
- **EGID** determines the process's group permissions.
- Linux uses these IDs to enforce security and access control.