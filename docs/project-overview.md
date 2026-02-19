# DHCP Relay Agent – Detailed Documentation

## Objective

To configure a Cisco router as a DHCP Relay Agent so that clients in the 192.168.1.0/24 network can receive IP addresses from a DHCP server located in the 192.168.2.0/24 network.

---

## Why DHCP Relay is Needed

DHCP uses broadcast messages to discover servers.  
Routers do not forward broadcast packets by default.

Therefore, we configure:

```
ip helper-address 192.168.2.5
```

This command forwards DHCP requests to the remote server.

---

## Networks Used

LAN Network: 192.168.1.0/24  
Server Network: 192.168.2.0/24  

---

## Key Concept

The `ip helper-address` command forwards the following UDP services:

- DHCP
- TFTP
- DNS
- NetBIOS
- Time Service

In this project, it forwards DHCP requests to the remote DHCP server.
