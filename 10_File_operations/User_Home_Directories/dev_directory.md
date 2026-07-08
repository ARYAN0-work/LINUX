# `/dev`, `/var`, and `/boot` Directories

---

# `/dev` Directory

The `/dev` directory contains **device files** that represent hardware devices connected to the Linux system.

Everything in Linux is treated like a file, including hardware devices.

## Examples

```text
/dev/sda1      → First partition on the first hard disk
/dev/lp1       → Second printer
/dev/random    → Source of random numbers
```

---

## Common Device Files

| Device File | Description |
|-------------|-------------|
| `/dev/sda` | First hard disk |
| `/dev/sda1` | First partition on the first disk |
| `/dev/null` | Discards all data written to it |
| `/dev/zero` | Produces unlimited zero bytes |
| `/dev/random` | True random number generator |
| `/dev/urandom` | Pseudo-random number generator |
| `/dev/tty` | Current terminal |

---

# `/var` Directory

The `/var` directory stores **variable data** that changes while the system is running.

Unlike `/usr`, the contents of `/var` constantly grow or change.

Common contents:

```text
/var/log      → System log files
/var/spool    → Print queues and mail queues
/var/tmp      → Temporary files
/var/lib      → Packages and application databases
```

---

## Common Subdirectories

| Directory | Purpose |
|-----------|---------|
| `/var/log` | System logs |
| `/var/lib` | Application databases |
| `/var/tmp` | Temporary files |
| `/var/spool` | Print/mail queues |
| `/var/cache` | Cached application data |

---

# `/boot` Directory

The `/boot` directory contains everything required for the Linux system to boot.

It stores the Linux kernel, initial RAM filesystem, bootloader files, and kernel configuration.

---

## Important Files

### `vmlinuz`

Compressed Linux kernel.

Required during system startup.

---

### `initramfs`

Initial RAM filesystem loaded before the real root filesystem.

Used during boot to initialize hardware and load drivers.

---

### `config`

Kernel configuration file.

Mostly used for debugging and development.

---

### `System.map`

Kernel symbol table.

Useful mainly for kernel debugging.

---

## Bootloader Configuration Files

Depending on the Linux distribution, the bootloader configuration is stored in:

```text
/boot/grub/grub.conf
```

or

```text
/boot/grub2/grub2.cfg
```

---

# Summary

## `/dev`

- Contains device files.
- Represents hardware as files.
- Examples:
  - `/dev/sda1`
  - `/dev/random`
  - `/dev/null`

---

## `/var`

Stores data that changes frequently.

Examples:

- Logs
- Temporary files
- Print queues
- Package databases

---

## `/boot`

Contains everything needed to boot Linux.

Includes:

- Linux kernel (`vmlinuz`)
- Initial RAM filesystem (`initramfs`)
- Kernel configuration (`config`)
- Kernel symbol table (`System.map`)
- GRUB configuration files