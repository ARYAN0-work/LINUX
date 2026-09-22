# IP Address

An **IP (Internet Protocol) address** is a unique numerical identifier assigned to every device connected to a network. It allows devices to identify each other and send or receive data over local networks or the Internet.

## IPv4

IPv4 uses a **32-bit** address written as four decimal numbers separated by dots.

### Example

```text
192.168.1.10
172.20.161.0
157.28.162.2
```

- 32-bit address
- About **4.3 billion** possible addresses
- Most widely used today

---

## IPv6

IPv6 was introduced to solve the shortage of IPv4 addresses. It uses a **128-bit** hexadecimal address separated by colons.

### Example

```text
2002:db8::8a3f:362:7897
```

- 128-bit address
- About **340 undecillion** possible addresses
- Supports a much larger number of devices
- Gradually replacing IPv4

---

## Public vs Private IP Addresses

### Private IP Address

Used inside a local network (home, office, etc.) and **cannot be accessed directly from the Internet**.

Common private IP ranges:

```text
10.0.0.0 - 10.255.255.255
172.16.0.0 - 172.31.255.255
192.168.0.0 - 192.168.255.255
```

### Public IP Address

Assigned by an Internet Service Provider (ISP) and is **globally unique**. Devices use public IPs to communicate over the Internet.

---

## NAT (Network Address Translation)

A router uses **NAT** to translate multiple private IP addresses into a single public IP address.

### Example

```text
PC1 (10.0.0.1)
PC2 (10.0.0.2)
PC3 (10.0.0.3)
        │
     Router (NAT)
     Public IP:
    200.88.1.11
        │
     Internet
        │
Server: 200.100.10.10
```

This allows multiple devices on a local network to share a single public IP while keeping internal addresses private.