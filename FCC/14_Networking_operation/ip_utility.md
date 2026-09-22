# `ip` Utility

The `ip` command is the modern Linux networking utility used to view and manage network interfaces, IP addresses, routing tables, and more.

It is part of the **iproute2** package and replaces older tools like `ifconfig` and `route`.

---

# Show IP Addresses

Display all network interfaces and their assigned IP addresses.

```bash
/sbin/ip addr show
```

or simply

```bash
ip addr show
```

Shows:

- Network interfaces
- IPv4 and IPv6 addresses
- MAC addresses
- Interface status (UP/DOWN)

---

# Show Routing Table

Display the system's routing information.

```bash
/sbin/ip route show
```

or

```bash
ip route show
```

Shows:

- Default gateway
- Network routes
- Destination networks
- Gateway used for each route
- Network interfaces used for routing

---

# Why Use `ip`?

- View IP addresses
- Check network interfaces
- Display routing information
- Configure networking
- Modern replacement for legacy networking commands

---

# Common `ip` Commands

| Command | Purpose |
|---------|---------|
| `ip addr show` | Display IP addresses and interfaces. |
| `ip route show` | Display the routing table. |
| `ip link show` | Display network interfaces. |
| `ip neigh` | Show the ARP/neighbor table. |

---

# Summary

- `ip` is the standard Linux networking utility.
- `ip addr show` displays network interfaces and assigned IP addresses.
- `ip route show` displays the routing table and default gateway.
- It is part of the **iproute2** package and replaces older networking tools like `ifconfig` and `route`.