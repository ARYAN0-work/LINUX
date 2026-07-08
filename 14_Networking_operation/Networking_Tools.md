# Networking Tools

Linux provides several command-line tools for testing connectivity, resolving hostnames, and troubleshooting DNS.

---

# `/etc/hosts`

The `/etc/hosts` file stores **local hostname-to-IP mappings**.

```bash
cat /etc/hosts
```

Example:

```text
127.0.0.1      localhost
127.0.1.1      ubuntu

192.168.1.212  wally
192.168.1.200  theodore
```

### Features

- Maps hostnames directly to IP addresses.
- Can assign multiple names to the same IP.
- Checked before querying DNS servers.

---

# Testing Hostname Resolution

After adding an entry to `/etc/hosts`, the hostname can be used directly.

```bash
ping theodore
```

Output:

```text
PING theodore (192.168.1.200)
64 bytes from theodore...
```

This confirms that the hostname was successfully resolved to its IP address.

---

# `host`

The `host` command performs DNS lookups.

```bash
host linuxfoundation.org
```

Example output:

```text
linuxfoundation.org has address 23.185.0.4
linuxfoundation.org has IPv6 address ...
linuxfoundation.org mail is handled by ...
```

It displays:

- IPv4 (A) records
- IPv6 (AAAA) records
- Mail (MX) records
- Other DNS information

---

# `nslookup`

Queries DNS servers for hostname resolution.

```bash
nslookup linuxfoundation.org
```

Example output:

```text
Server: 127.0.0.53

Name: linuxfoundation.org
Address: 23.185.0.4
```

Useful for checking which DNS server is answering your requests.

---

# `dig`

`dig` (**Domain Information Groper**) is the most detailed DNS lookup tool.

```bash
dig linuxfoundation.org
```

Example output:

```text
QUESTION SECTION:
linuxfoundation.org. IN A

ANSWER SECTION:
linuxfoundation.org. 5 IN A 23.185.0.4
```

It provides:

- Query details
- Answer section
- Authority section
- Additional records
- Query time
- DNS server used

---

# Common Networking Commands

| Command | Purpose |
|---------|---------|
| `ping` | Test network connectivity. |
| `host` | Simple DNS lookup. |
| `nslookup` | Query DNS servers. |
| `dig` | Detailed DNS diagnostics. |
| `cat /etc/hosts` | View local hostname mappings. |
| `cat /etc/resolv.conf` | View DNS server configuration. |

---

# Summary

- `/etc/hosts` stores local hostname mappings.
- `ping` verifies hostname resolution and connectivity.
- `host` performs quick DNS lookups.
- `nslookup` queries DNS servers directly.
- `dig` provides detailed DNS information and is commonly used for troubleshooting.