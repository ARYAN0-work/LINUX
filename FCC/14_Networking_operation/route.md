# Routing Commands

Linux provides commands to view and manage the system's routing table. Modern systems use the **`ip`** utility, while older systems use the **`route`** command.

---

# View Routing Table

Display the current routing table.

```bash
route -n
```

or

```bash
ip route
```

The routing table shows:

- Destination networks
- Gateway addresses
- Network interfaces
- Route metrics

---

# Add a Static Route

Add a route to a specific network.

Legacy command:

```bash
route add -net <network> gw <gateway>
```

Modern command:

```bash
ip route add <network> via <gateway>
```

Example:

```bash
ip route add 192.168.2.0/24 via 192.168.1.1
```

---

# Delete a Static Route

Remove an existing route.

Legacy command:

```bash
route del -net <network>
```

Modern command:

```bash
ip route del <network>
```

Example:

```bash
ip route del 192.168.2.0/24
```

---

# Legacy vs Modern Commands

| Task | Legacy | Modern |
|------|--------|--------|
| View routes | `route -n` | `ip route` |
| Add route | `route add` | `ip route add` |
| Delete route | `route del` | `ip route del` |

---

# Summary

- `ip route` is the modern command for viewing and managing routes.
- `route` is an older utility kept mainly for compatibility.
- Static routes can be added or removed using either tool.
- Routing tables determine how packets reach different networks.