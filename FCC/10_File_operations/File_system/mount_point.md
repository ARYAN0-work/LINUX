# Mount Points in Linux

A **mount point** is a directory where a filesystem is attached (mounted) so that its files become accessible through the Linux directory tree.

Linux treats every storage device as part of one unified filesystem rooted at `/`.

---

## Example

The following diagram shows three partitions mounted at different locations.

```text
            Mount Points

            (/)      (/home)      (/var)
             │           │            │
         /dev/sda1   /dev/sda5   /dev/sda6
               \         |         /
                \        |        /
                 \       |       /
                    /dev/sda
```

- `/dev/sda1` is mounted as the **root filesystem (`/`)**
- `/dev/sda5` is mounted as **`/home`**
- `/dev/sda6` is mounted as **`/var`**

Each partition becomes accessible through its mount point.

---

## Mount Command

To mount a filesystem:

```bash
sudo mount /dev/sda5 /home
```

### Syntax

```bash
sudo mount <device> <mount_point>
```

### Example

```bash
sudo mount /dev/sda5 /home
```

This attaches the partition `/dev/sda5` to the `/home` directory.

---

## Unmount Command

To detach (unmount) a mounted filesystem:

```bash
sudo umount /home
```

### Syntax

```bash
sudo umount <mount_point>
```

or

```bash
sudo umount <device>
```

Examples:

```bash
sudo umount /home
```

```bash
sudo umount /dev/sda5
```

> **Note:** The command is **`umount`**, **not** `unmount`.

---

## Common Mount Points

| Mount Point | Purpose |
|-------------|---------|
| `/` | Root filesystem |
| `/home` | User home directories |
| `/var` | Variable data (logs, cache, mail, etc.) |
| `/boot` | Bootloader and kernel files |
| `/mnt` | Temporary mount location |
| `/media` | Automatically mounted removable devices |

---

## Key Points

- A **mount point** is simply a directory.
- Linux makes partitions accessible by mounting them to directories.
- One partition can be mounted at one mount point at a time.
- Use `mount` to attach a filesystem.
- Use `umount` to safely detach it before removing the storage device.

# Mount Points in Linux

A **mount point** is a directory where a filesystem is attached (mounted) so that its files become accessible through the Linux directory tree.

Linux treats every storage device as part of one unified filesystem rooted at `/`.

---

## Example

The following diagram shows three partitions mounted at different locations.

```text
            Mount Points

            (/)      (/home)      (/var)
             │           │            │
         /dev/sda1   /dev/sda5   /dev/sda6
               \         |         /
                \        |        /
                 \       |       /
                    /dev/sda
```

- `/dev/sda1` is mounted as the **root filesystem (`/`)**
- `/dev/sda5` is mounted as **`/home`**
- `/dev/sda6` is mounted as **`/var`**

Each partition becomes accessible through its mount point.

---

## Mount Command

To mount a filesystem:

```bash
sudo mount /dev/sda5 /home
```

### Syntax

```bash
sudo mount <device> <mount_point>
```

### Example

```bash
sudo mount /dev/sda5 /home
```

This attaches the partition `/dev/sda5` to the `/home` directory.

---

## Unmount Command

To detach (unmount) a mounted filesystem:

```bash
sudo umount /home
```

### Syntax

```bash
sudo umount <mount_point>
```

or

```bash
sudo umount <device>
```

Examples:

```bash
sudo umount /home
```

```bash
sudo umount /dev/sda5
```

> **Note:** The command is **`umount`**, **not** `unmount`.

---

## Common Mount Points

| Mount Point | Purpose |
|-------------|---------|
| `/` | Root filesystem |
| `/home` | User home directories |
| `/var` | Variable data (logs, cache, mail, etc.) |
| `/boot` | Bootloader and kernel files |
| `/mnt` | Temporary mount location |
| `/media` | Automatically mounted removable devices |

---

## Key Points

- A **mount point** is simply a directory.
- Linux makes partitions accessible by mounting them to directories.
- One partition can be mounted at one mount point at a time.
- Use `mount` to attach a filesystem.
- Use `umount` to safely detach it before removing the storage device.