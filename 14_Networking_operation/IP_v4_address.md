# Decoding IPv4 Addresses

An IPv4 address consists of **32 bits**, divided into **4 octets**. Each octet contains **8 bits** and is represented as a decimal number ranging from **0 to 255**.

## Binary Representation

Each decimal octet is stored in binary.

### Example

```text
IPv4 Address:
172.16.31.46

Binary:
10101100.00010000.00011111.00101110
```

---

## IPv4 Address Classes

IPv4 addresses were traditionally divided into classes based on how many bits were used for the **Network ID** and **Host ID**.

| Class | Network ID | Host ID | Purpose |
|-------|------------|---------|---------|
| **A** | 1st octet | Last 3 octets | Very large networks |
| **B** | First 2 octets | Last 2 octets | Medium-sized networks |
| **C** | First 3 octets | Last octet | Small networks |
| **D** | — | — | Multicast addresses |
| **E** | — | — | Reserved for future use |

### Example

```text
Class A
Network.Host.Host.Host

Class B
Network.Network.Host.Host

Class C
Network.Network.Network.Host
```

> **Note:** Modern networks primarily use **CIDR (Classless Inter-Domain Routing)** instead of class-based addressing, but understanding these classes helps explain how IPv4 addresses were originally organized.