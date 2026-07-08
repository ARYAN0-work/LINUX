# Class A, B & C Networks

IPv4 addresses were originally divided into **Class A**, **Class B**, and **Class C** based on how many bits were reserved for the **Network ID** and **Host ID**.

---

# Class A Network

Designed for **very large networks**.

## Structure

```text
0 | Network ID | Host ID
```

- First bit is always **0**.
- First **8 bits (1 octet)** identify the network.
- Remaining **24 bits (3 octets)** identify hosts.

### Address Range

```text
1.0.0.0  → 127.255.255.255
```

### Example

```text
IP Address:
10.233.45.23

Network ID : 10
Host ID    : 233.45.23
```

---

# Class B Network

Designed for **medium-sized networks**.

## Structure

```text
10 | Network ID | Host ID
```

- First **2 bits** are always **10**.
- First **16 bits (2 octets)** are the Network ID.
- Last **16 bits (2 octets)** are the Host ID.

### Address Range

```text
128.0.0.0 → 191.255.255.255
```

### Example

```text
IP Address:
135.201.18.1

Network ID : 135.201
Host ID    : 18.1
```

---

# Class C Network

Designed for **small networks**.

## Structure

```text
110 | Network ID | Host ID
```

- First **3 bits** are always **110**.
- First **24 bits (3 octets)** are the Network ID.
- Last **8 bits (1 octet)** are the Host ID.

### Address Range

```text
192.0.0.0 → 223.255.255.255
```

### Example

```text
IP Address:
192.33.84.156

Network ID : 192.33.84
Host ID    : 156
```

---

# Class D & Class E

| Class | Purpose | Address Range |
|--------|---------|---------------|
| **Class D** | Multicast addresses | **224.0.0.0 – 239.255.255.255** |
| **Class E** | Reserved for future/experimental use | **240.0.0.0 – 255.255.255.255** |

> **Note:** Modern networks no longer rely on class-based addressing. They use **CIDR (Classless Inter-Domain Routing)**, which is more flexible and efficient.

---

# Allocating IP Addresses

Devices can receive IP addresses in two ways.

## 1. Static IP (Manual)

- IP address is assigned manually by an administrator.
- Does not change unless reconfigured.
- Commonly used for:
  - Servers
  - Routers
  - Printers
  - Network devices

### Example

```text
Server → 192.168.1.10
```

---

## 2. Dynamic IP (DHCP)

- IP address is assigned automatically by a **DHCP (Dynamic Host Configuration Protocol)** server.
- Devices receive an available IP whenever they join the network.
- Commonly used for:
  - Laptops
  - Phones
  - Home computers
  - Guest devices

### Example

```text
Laptop joins Wi-Fi
        ↓
DHCP Server assigns:
192.168.1.25
```

### Advantages

- Automatic configuration
- Easier network management
- Prevents IP address conflicts
- Efficient reuse of available addresses