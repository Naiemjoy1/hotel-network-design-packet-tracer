# 🏨 Hotel Network Design

![Topology](https://i.ibb.co.com/nsH5xsc9/topology.png)

## Project Overview

This project presents the design and implementation of a **Hotel Network Infrastructure** using Cisco Packet Tracer. The hotel consists of three floors connected through serial links and configured with OSPF dynamic routing.

The project demonstrates enterprise networking concepts including VLAN segmentation, Inter-VLAN Routing, DHCP, SSH, Wireless Networking, and Port Security.

---

## Technologies Implemented

- Hierarchical Network Design
- VLAN Segmentation
- Router-on-a-Stick
- OSPF Routing Protocol
- DHCP Server Configuration
- SSH Remote Access
- Wireless LAN Configuration
- Port Security
- Inter-VLAN Routing
- Dynamic IP Address Allocation
- Network Testing and Verification

---

## Hotel Structure

### First Floor

| Department | VLAN | Network Address |
| ---------- | ---- | --------------- |
| Reception  | 80   | 192.168.8.0/24  |
| Store      | 70   | 192.168.7.0/24  |
| Logistics  | 60   | 192.168.6.0/24  |

### Second Floor

| Department      | VLAN | Network Address |
| --------------- | ---- | --------------- |
| Finance         | 50   | 192.168.5.0/24  |
| HR              | 40   | 192.168.4.0/24  |
| Sales/Marketing | 30   | 192.168.3.0/24  |

### Third Floor

| Department | VLAN | Network Address |
| ---------- | ---- | --------------- |
| IT         | 10   | 192.168.1.0/24  |
| Admin      | 20   | 192.168.2.0/24  |

---

## Router Interconnections

| Connection        | Network       |
| ----------------- | ------------- |
| Floor 1 ↔ Floor 2 | 10.10.10.8/30 |
| Floor 1 ↔ Floor 3 | 10.10.10.4/30 |
| Floor 2 ↔ Floor 3 | 10.10.10.0/30 |

---

## Network Topology

![Topology](https://i.ibb.co.com/nsH5xsc9/topology.png)

---

## VLAN Allocation

| VLAN ID | Department |
| ------- | ---------- |
| 10      | IT         |
| 20      | Admin      |
| 30      | Sales      |
| 40      | HR         |
| 50      | Finance    |
| 60      | Logistics  |
| 70      | Store      |
| 80      | Reception  |

---

## OSPF Configuration

The network uses **OSPF Process ID 10** to dynamically advertise all internal networks.

### OSPF Verification

![OSPF](https://i.ibb.co.com/v6rS4FNT/ospf.png)

---

## DHCP Configuration

Each router acts as a DHCP server for its respective VLANs.

Example:

```cisco
ip dhcp pool Reception
network 192.168.8.0 255.255.255.0
default-router 192.168.8.1
dns-server 192.168.8.1
```

---

## SSH Configuration

SSH is configured on all routers for secure remote management.

```cisco
ip domain-name testssh

username test password test

crypto key generate rsa

1024

line vty 0 15
login local
transport input ssh
```

---

## Port Security

Port Security is implemented on the IT Department switch using sticky MAC learning.

Configuration:

```cisco
interface fa0/1

switchport mode access

switchport access vlan 10

switchport port-security

switchport port-security maximum 1

switchport port-security mac-address sticky

switchport port-security violation shutdown
```

### Verification

![Port Security](https://i.ibb.co.com/FqnbH75g/sticky.png)

---

## Connectivity Testing

Devices from different VLANs communicate successfully through OSPF and Router-on-a-Stick implementation.

### Ping Verification

![Ping Test](https://i.ibb.co.com/ycBvJwQD/internal-ping.png)

---

## Features Completed

- ✅ VLAN Configuration
- ✅ Router-on-a-Stick
- ✅ OSPF Dynamic Routing
- ✅ DHCP Services
- ✅ SSH Remote Access
- ✅ Wireless Networking
- ✅ Port Security
- ✅ Printer Connectivity
- ✅ Dynamic IP Assignment
- ✅ Inter-VLAN Communication

---

## Project Structure

```text
Hotel-Network-Design/

├── README.md
├── Hotel-Network-Design.pkt
├── configs/
├── screenshots/
│   ├── topology.png
│   ├── ospf.png
│   ├── sticky.png
│   └── internal-ping.png
```

---

## Author

**Naiem Hasan**

Cisco Packet Tracer Project • 2026
