# Adding and Removing Users

Linux provides commands to create and delete user accounts. These operations typically require **root** or **sudo** privileges.

## Add a New User

Use the `useradd` command to create a new user.

```bash
sudo useradd username
```

**Example**

```bash
sudo useradd bjmoose
```

This creates a new user entry in the system.

---

## Remove an Existing User

Use the `userdel` command to delete a user account.

```bash
sudo userdel username
```

**Example**

```bash
sudo userdel bjmoose
```

> To remove the user's home directory as well:

```bash
sudo userdel -r bjmoose
```

---

## What Happens When a User Is Created?

After running `useradd`, Linux adds a new entry to the `/etc/passwd` file.

Example:

```text
bjmoose:x:1002:1002::/home/bjmoose:/bin/bash
```

### Breakdown

| Field | Description |
|-------|-------------|
| `bjmoose` | Username |
| `x` | Password placeholder (actual password is stored in `/etc/shadow`) |
| `1002` | User ID (UID) |
| `1002` | Primary Group ID (GID) |
| *(empty)* | User information (GECOS field) |
| `/home/bjmoose` | Home directory |
| `/bin/bash` | Default login shell |

> **Note:** The `useradd` command creates the user account. Depending on the Linux distribution, you may also need to create the home directory (`-m`) and set a password separately using `passwd`.

## ON UBNUTU

# User Home Directory

When a new user is created, Linux creates a **home directory** containing default configuration files copied from `/etc/skel`.

## Example

Create a user with a home directory:

```bash
sudo useradd -m -c "Eric Dolphy" -s /bin/bash edolphy
```

Set a password:

```bash
sudo passwd edolphy
```

Verify the user:

```bash
grep edolphy /etc/passwd
grep edolphy /etc/group
```

Example output:

```text
edolphy:x:1001:1001:Eric Dolphy:/home/edolphy:/bin/bash
```

---

## Default Files

List the user's home directory:

```bash
ls -la /home/edolphy
```

Typical files:

- `.bashrc`
- `.profile`
- `.bash_logout`

These files are copied from:

```bash
ls -la /etc/skel
```

---

## Remove the User

Delete the user and its home directory:

```bash
sudo userdel -r edolphy
```

Verify removal:

```bash
ls -l /home
```

> **Note:** `/etc/skel` acts as a template directory. Every new user receives copies of these default startup files.