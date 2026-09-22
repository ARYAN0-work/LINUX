# Basics of Users and Groups

Linux is a **multi-user operating system**, allowing multiple users to access the same system while keeping their files and permissions separate.

## User

A **user** is an individual account that can log in and use the system.

Examples:

- `root`
- `student`
- `john`

Each user has:

- A unique **User ID (UID)**
- A home directory (`/home/username`)
- A default shell (such as Bash)

---

## Group

A **group** is a collection of users that share the same permissions.

Examples:

- `developers`
- `admins`
- `students`

Each group has a unique **Group ID (GID)**.

---

## Why Groups?

Groups make permission management easier.

Instead of giving permissions to each user individually, you assign permissions to a group, and every member inherits those permissions.

```text
developers
├── Alice
├── Bob
└── Charlie
```

---

> **Summary:** A **user** represents a person or account, while a **group** is a collection of users used to simplify permission management.