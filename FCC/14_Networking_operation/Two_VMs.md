# SSH & SCP Between Two Virtual Machines

This demonstration shows two Linux virtual machines communicating securely using **SSH** and **SCP**.

---

# Step 1: Check the Server's IP Address

On the remote machine:

```bash
ip -brief addr show
```

Find the IP address of the machine (for example, `172.16.249.193`).

---

# Step 2: Connect Using SSH

From the local machine:

```bash
ssh student@172.16.249.193
```

The first time you connect, you'll see:

```text
Are you sure you want to continue connecting (yes/no)?
```

Type:

```text
yes
```

Then enter the user's password.

---

# Step 3: Execute Commands Remotely

After logging in, you can run any Linux command on the remote machine.

Example:

```bash
ls
```

View files on the remote system.

---

# Step 4: Transfer Files Using SCP

Copy a local file to the remote machine:

```bash
scp file.txt student@172.16.249.193:/tmp
```

The file is securely copied over SSH.

---

# What Happened?

- Local machine discovered the server's IP.
- SSH established an encrypted connection.
- Commands were executed on the remote machine.
- SCP securely transferred files between the two systems.

---

# Summary

- Use `ip -brief addr show` to find the server IP.
- Use `ssh user@ip` to access a remote Linux machine.
- Accept the host key the first time you connect.
- Use `scp` to securely transfer files over SSH.
- SSH and SCP are fundamental tools for Linux server administration.