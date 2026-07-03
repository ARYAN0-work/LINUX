## Network Connection Types in Linux

Linux supports multiple ways to connect to a network. Whether you're using a laptop, desktop, or server, the operating system provides tools to configure and manage these connections.

### 📶 Wireless Internet (Wi-Fi)

A **wireless internet connection** allows your system to connect to a Wi-Fi router without using any cables.

- Uses a wireless network adapter.
- Commonly used in laptops and personal computers.
- Can be configured using either the **Graphical Interface (GUI)** or the **Terminal** (e.g., `nmcli`, `iwctl`).

---

### 📱 Mobile Broadband

**Mobile broadband** provides internet access through a cellular network (3G, 4G, or 5G).

- Uses a USB modem, mobile hotspot, or SIM-enabled device.
- Useful when Wi-Fi or Ethernet is unavailable.
- Linux supports mobile broadband through NetworkManager and other networking tools.

---

### 🔌 Wired Network (Ethernet)

A **wired network** connects the computer directly to a router or switch using an Ethernet cable.

- Generally faster and more stable than Wi-Fi.
- Commonly used on servers and desktop computers.
- Preferred for data centers, development machines, and production environments.

---

## Diagram

```text
                 Wireless Internet
                        ▲
                        │
                        │
      Mobile Broadband ◄── 📶 ──►
                        │
                        ▼
                 Wired Network
```

---

## 💡 Note for DevOps & Backend Developers

As a backend or DevOps engineer, you'll mostly configure network connections using the **terminal** rather than the graphical interface. Commands and tools you'll encounter later include:

- `ip` – Display and configure network interfaces.
- `ping` – Check network connectivity.
- `nmcli` – Manage NetworkManager from the terminal.
- `ssh` – Connect to remote Linux machines securely.
- `curl` / `wget` – Communicate with web servers and download resources.

Understanding these networking concepts is essential because almost every server you work with will rely on one of these connection methods.

# Basic Computer Network Architecture

A **computer network** is a collection of interconnected devices that communicate with each other to share data and resources. Different networking devices work together to ensure data reaches its intended destination securely and efficiently.

---

## Network Diagram

```text
                    Internet
                        │
                     Firewall
                        │
                     Router
                    /      \
             Switch        Hub
            /   |   \     / | \
       Laptop PC  AP   Server PC Workstation
                  │
              Wireless Devices
```

---

## Components of the Network

### 🌐 Internet

The **Internet** is a global network that connects millions of computers and networks worldwide. It allows users to access websites, cloud services, emails, and other online resources.

---

### 🛡️ Firewall

A **Firewall** is a security device or software that monitors incoming and outgoing network traffic.

- Blocks unauthorized access.
- Allows trusted communication.
- Protects the internal network from external threats.

---

### 📡 Router

A **Router** connects different networks together, typically connecting your local network (LAN) to the Internet.

**Responsibilities:**

- Routes data packets between networks.
- Assigns IP addresses using DHCP (in most home networks).
- Connects wired and wireless devices to the Internet.

---

### 🔀 Switch

A **Switch** connects multiple devices within the same Local Area Network (LAN).

- Uses **MAC addresses** to forward data.
- Faster and more efficient than a hub.
- Commonly used in offices and data centers.

Example connected devices:

- Laptop
- Desktop
- Wireless Access Point (AP)

---

### 📶 Wireless Access Point (AP)

An **Access Point (AP)** provides wireless connectivity to devices.

It connects wireless devices such as:

- Laptops
- Smartphones
- Tablets

to the wired network.

---

### 🔄 Hub

A **Hub** is an older networking device that simply broadcasts incoming data to **every connected device**.

Characteristics:

- Does not understand MAC addresses.
- Less efficient than a switch.
- Rarely used in modern networks.

---

### 🖥️ Server

A **Server** is a computer that provides services or resources to other computers on the network.

Examples:

- Web Server
- Database Server
- File Server
- Application Server

---

### 💻 Client Devices

These are devices that use the network services.

Examples include:

- Laptop
- Desktop PC
- Workstation
- Mobile Devices

---

## Data Flow

When a computer requests a website:

```text
Computer
    │
    ▼
 Switch
    │
    ▼
 Router
    │
    ▼
 Firewall
    │
    ▼
 Internet
```

The response follows the reverse path back to the computer.

---

## 💡 Note for DevOps & Backend Developers

Understanding this architecture is important because you'll regularly work with:

- Servers deployed behind routers and firewalls.
- SSH connections to remote machines.
- Docker containers communicating over networks.
- Reverse proxies (Nginx/Apache).
- Cloud networking (AWS VPC, Azure VNet, GCP VPC).
- Load balancers, switches, and network security rules.

A strong understanding of these networking fundamentals makes debugging server and deployment issues much easier.

# MAC (Media Access Control) Address

A **MAC (Media Access Control) Address** is a **unique physical (hardware) address** assigned to every **Network Interface Card (NIC)** by the manufacturer. It is used to identify a device on a **local network (LAN)**.

Unlike an IP address, which can change, a MAC address is usually **permanently assigned** to the network hardware.

---

## Structure of a MAC Address

Example:

```text
00:1A:3F:F1:4C:C6
```

A MAC address consists of **48 bits (6 bytes)** represented as **12 hexadecimal digits**.

```text
00    : 1A    : 3F    : F1    : 4C    : C6
│                 │
├── First 3 bytes ──► OUI (Organizationally Unique Identifier)
│                     Identifies the manufacturer (e.g., Intel, Dell, Cisco).
│
└── Last 3 bytes ───► Device Identifier
                      Uniquely identifies the specific network interface
                      assigned by the manufacturer.
```

---

## Why is a MAC Address Important?

- Every network device has a unique MAC address.
- Used for communication within a **Local Area Network (LAN)**.
- Switches use MAC addresses to forward data to the correct device.
- Works at **Layer 2 (Data Link Layer)** of the OSI Model.

---

## MAC Address vs IP Address

| MAC Address | IP Address |
|-------------|------------|
| Physical (hardware) address | Logical address |
| Assigned by manufacturer | Assigned by router or ISP |
| Usually permanent | Can change |
| Used inside a local network | Used to communicate across networks |
| Layer 2 (Data Link) | Layer 3 (Network) |

---

## How to View Your MAC Address in Linux

```bash
ip link
```

or

```bash
ifconfig
```

Example output:

```text
link/ether 08:00:27:3b:8f:1a
```

Here, `08:00:27:3b:8f:1a` is the MAC address.

---

## 💡 Note for DevOps & Backend Developers

Although you'll mostly work with **IP addresses**, understanding MAC addresses is essential because:

- Every network packet on a local network is ultimately delivered using MAC addresses.
- Network troubleshooting often involves checking MAC addresses.
- Docker, virtual machines, and cloud networking all assign virtual MAC addresses.
- You'll encounter MAC addresses while working with switches, ARP, and network diagnostics.

### THERES SOFTWARE MANAGER LIKE NPM USED TO RUN DISTRO +> A VERY BIG STORY [1:50-2:00] => the whole story 