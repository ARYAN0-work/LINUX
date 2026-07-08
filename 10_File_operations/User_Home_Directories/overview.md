# User Home Directories

In Linux, every user has a **home directory** where their personal files, documents, and configuration files are stored.

The default location for user home directories is:

```text
/home
```

---

## Home Directory Structure

Example:

```text
/home
├── beaver
├── wally
├── staff
│   ├── ward
│   └── june
```

Each folder represents a user's personal workspace.

---

## Typical Organization

Depending on the environment, home directories can also be organized by groups.

For example, a school or university might organize users like this:

```text
/home/faculty/
/home/staff/
/home/students/
```

Each group directory can then contain individual user accounts.

Example:

```text
/home
├── faculty
│   ├── professor1
│   └── professor2
│
├── staff
│   ├── admin1
│   └── admin2
│
└── students
    ├── alice
    ├── bob
    └── charlie
```

---

## What is Stored in a Home Directory?

A user's home directory typically contains:

- Personal documents
- Downloads
- Pictures
- Videos
- Music
- Desktop files
- Application configuration files (hidden files)
- Projects and source code

Example:

```text
/home/alice
├── Documents
├── Downloads
├── Pictures
├── Projects
├── Music
├── Videos
└── .bashrc
```

---

## Key Points

- `/home` stores user home directories.
- Every user usually has a separate home directory.
- Users normally have full access to their own home directory.
- Home directories can be organized by departments or groups (e.g., `faculty`, `staff`, `students`).
- User-specific configuration files are stored as hidden files (their names begin with `.`).