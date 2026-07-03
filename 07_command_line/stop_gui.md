# Switching Between GUI and Terminal

## GUI vs Terminal

* **GUI (Graphical User Interface)** → Desktop environment with windows, icons, mouse, etc.
* **Terminal (CLI)** → Text-based interface used to run Linux commands.

---

## Stop the GUI

```bash
sudo systemctl stop gdm
```

or (older method)

```bash
sudo telinit 3
```

This stops the graphical desktop and switches to the command-line interface.

---

## Start the GUI

```bash
sudo systemctl start gdm
```

or (older method)

```bash
sudo telinit 5
```

This starts the graphical desktop again.

---

## What is `gdm`?

**GDM (GNOME Display Manager)** is the program that starts the login screen and launches the GNOME desktop.

Older Ubuntu versions may use:

```text
lightdm
```

instead of:

```text
gdm
```

---

## What is `systemctl`?

`systemctl` is the modern command used to manage Linux services.

Common examples:

```bash
sudo systemctl start <service>
sudo systemctl stop <service>
sudo systemctl restart <service>
systemctl status <service>
```

Example:

```bash
sudo systemctl restart nginx
```

---

## What is `telinit`?

`telinit` is an older command used to switch Linux runlevels.

* `telinit 3` → Command-line mode
* `telinit 5` → Graphical mode

Today, `systemctl` is preferred on modern Linux systems.

---

## Do I Need to Learn This?

### Learn Well ✅

* `systemctl start`
* `systemctl stop`
* `systemctl restart`
* `systemctl status`

### Just Know the Concept 📚

* `telinit`
* `gdm`
* `lightdm`

These are useful to understand but are used much less on modern Linux systems.

---

## Key Takeaway

As a **Backend Developer** or **DevOps Engineer**, you'll use **`systemctl`** frequently to manage services like Nginx, Docker, PostgreSQL, Redis, and your own applications. Understanding `telinit` and display managers (`gdm`/`lightdm`) is good background knowledge, but they are not commands you'll use every day.
