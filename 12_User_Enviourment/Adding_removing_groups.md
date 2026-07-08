# Adding and Removing Groups

Linux groups are managed using the `groupadd` command, while users can be added or removed from groups using `usermod`.

## Create a New Group

```bash
sudo groupadd anewgroup
```

---

## Add a User to a Group

Use the `-aG` options to append the user to an additional group.

```bash
sudo usermod -aG anewgroup rjsquirrel
```

Verify:

```bash
groups rjsquirrel
```

Example output:

```text
rjsquirrel : rjsquirrel anewgroup
```

> The `-a` option **appends** the new group, while `-G` specifies the supplementary groups.

---

## Remove a User from a Group

If you omit `-a`, the user's supplementary groups are replaced.

```bash
sudo usermod -G rjsquirrel rjsquirrel
```

Verify:

```bash
groups rjsquirrel
```

Example output:

```text
rjsquirrel : rjsquirrel
```

> **Note:** Be careful when using `usermod -G` without `-a`, as it removes the user from all other supplementary groups.