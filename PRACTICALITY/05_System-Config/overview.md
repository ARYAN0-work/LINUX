1. Linux Network Connection Types

Linux can connect to networks through:

- Wi-Fi → wireless
- Mobile broadband → 4G/5G, hotspot, modem
- Ethernet → cable

For DevOps, Ethernet + server networking matter the most.

Useful commands we'll learn later:

ip
ping
nmcli
ssh
curl
wget

# Basic Network Architecture

Think:

Your Computer
     ↓
   Switch
     ↓
  Router
     ↓
 Firewall
     ↓
 Internet

# Router

Connects different networks.

Example:

Home LAN ↔ Internet 

````bash
Switch

Connects devices inside the same LAN.

PC
 │
Switch ── Server
 │
Laptop
Access Point

Provides Wi-Fi and connects wireless devices to the network.

Hub

Old device that sends data to everyone. Mostly obsolete.

Firewall

Controls network traffic and can block unauthorized connections.

Server

Provides services:

Web server
Database server
File server
Application server
Client

Uses those services.

````

3. MAC Address

> A MAC address identifies a network interface on the local network.

Example:

08:00:27:3b:8f:1a

It's a Layer 2 concept.

A switch uses MAC addresses to decide where to send frames.

MAC vs IP

> Simple mental model:

MAC → local network identity
IP  → network/address identity

Don't get stuck on "physical address = permanently fixed." Modern systems can use virtual/randomized MAC addresses, so just remember the basic concept.

4. See your MAC address

The important command here is:

> ip link

You'll see something like:

link/ether 08:00:27:3b:8f:1a

That value is the MAC address.

ifconfig exists too, but don't prioritize it. ip is the modern tool we'll focus on.s

# 5. The NPM Analogy

Your note:

"Software manager like NPM used to run distro"


```bash

The useful idea is:

Linux distribution
       ↓
Package manager
       ↓
Install/manage software

For Ubuntu:

Ubuntu
  ↓
APT
  ↓
Packages

This is similar conceptually to:

Node.js
   ↓
 npm
   ↓
 packages

But they're not the same thing.

For example:

sudo apt install nginx

means:

Ubuntu's package manager downloads and installs Nginx and its required packages.

This is a very important DevOps concept, and we'll go deeper into package management later.

For this chunk:

🟢 Learn: Router, switch, firewall, server/client, MAC vs IP, ip link

🟡 Understand: Wi-Fi, mobile broadband, Ethernet

🔴 Don't memorize: OSI-layer details, OUI structure, hub internals, etc.

```