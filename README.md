# Modern Hotel Network Design using Cisco Packet Tracer

## Project Overview

This project implements a complete enterprise hotel network infrastructure for **Vic Modern Hotel** using Cisco Packet Tracer.

The hotel consists of three floors interconnected through routers using serial links and OSPF routing.

Technologies implemented:

- Hierarchical Network Design
- VLAN Segmentation
- Router-on-a-Stick
- OSPF Routing
- DHCP Services
- SSH Remote Access
- WLAN Configuration
- Port Security
- Inter-VLAN Routing
- Dynamic Address Allocation
- Network Testing and Verification

---

# Hotel Structure

## Floor 1

| Department | VLAN | Network        |
| ---------- | ---- | -------------- |
| Reception  | 80   | 192.168.8.0/24 |
| Store      | 70   | 192.168.7.0/24 |
| Logistics  | 60   | 192.168.6.0/24 |

---

## Floor 2

| Department | VLAN | Network        |
| ---------- | ---- | -------------- |
| Finance    | 50   | 192.168.5.0/24 |
| HR         | 40   | 192.168.4.0/24 |
| Sales      | 30   | 192.168.3.0/24 |

---

## Floor 3

| Department | VLAN | Network        |
| ---------- | ---- | -------------- |
| IT         | 10   | 192.168.1.0/24 |
| Admin      | 20   | 192.168.2.0/24 |

---

# Router Interconnections

| Link            | Network       |
| --------------- | ------------- |
| Floor1 ↔ Floor2 | 10.10.10.8/30 |
| Floor1 ↔ Floor3 | 10.10.10.4/30 |
| Floor2 ↔ Floor3 | 10.10.10.0/30 |

---

# Features Implemented

✔ VLAN Configuration

✔ Router-on-a-Stick

✔ OSPF Routing

✔ DHCP Server Configuration

✔ SSH Configuration

✔ Wireless Networks

✔ Port Security

✔ Sticky MAC Address Learning

✔ Inter-VLAN Communication

✔ Printer Connectivity

✔ Dynamic IP Assignment

---

# Network Topology

![Topology](images/topology.png)

---

# Floor 1 Configuration

### VLANs

| VLAN | Department |
| ---- | ---------- |
| 80   | Reception  |
| 70   | Store      |
| 60   | Logistics  |

### Router Subinterfaces

```cisco
interface g0/0.80
encapsulation dot1Q 80
ip address 192.168.8.1 255.255.255.0

interface g0/0.70
encapsulation dot1Q 70
ip address 192.168.7.1 255.255.255.0

interface g0/0.60
encapsulation dot1Q 60
ip address 192.168.6.1 255.255.255.0
```

---

# OSPF Configuration

```cisco
router ospf 10

network 10.10.10.0 0.0.0.3 area 0

network 10.10.10.4 0.0.0.3 area 0

network 10.10.10.8 0.0.0.3 area 0

network 192.168.0.0 0.0.255.255 area 0
```

---

# DHCP Configuration Example

```cisco
ip dhcp pool Reception

network 192.168.8.0 255.255.255.0

default-router 192.168.8.1

dns-server 192.168.8.1
```

---

# SSH Configuration

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

# Port Security

Configured in IT Department Switch

```cisco
interface fa0/1

switchport mode access

switchport access vlan 10

switchport port-security

switchport port-security maximum 1

switchport port-security mac-address sticky

switchport port-security violation shutdown
```

---

# Verification

## OSPF Neighbors

![OSPF](images/ospf-neighbor.png)

---

## Routing Table

![Route](images/routing-table.png)

---

## DHCP Lease

![DHCP](images/dhcp.png)

---

## SSH Login

![SSH](images/ssh.png)

---

## Port Security

![PortSecurity](images/port-security.png)

---

## Successful Ping Test

![Ping](images/ping-test.png)

---

# Project Files

```
Vic-Modern-Hotel/
│
├── README.md
├── topology.pkt
├── configs
│   ├── Floor1-Router.txt
│   ├── Floor2-Router.txt
│   ├── Floor3-Router.txt
│   ├── Switch1.txt
│   ├── Switch2.txt
│   └── Switch3.txt
│
└── images
    ├── topology.png
    ├── ospf-neighbor.png
    ├── routing-table.png
    ├── ssh.png
    ├── dhcp.png
    ├── ping-test.png
    └── port-security.png
```

---

# Testing Results

✔ Inter-VLAN Communication Successful

✔ DHCP Address Assignment Successful

✔ OSPF Neighbor Adjacencies Established

✔ SSH Remote Access Successful

✔ Wireless Clients Connected

✔ Port Security Working Correctly

✔ All Departments Reachable

---

# Author

**Naiem Hasan**

Cisco Packet Tracer Project

CCNA Networking Practice

2026

https://ibb.co.com/DHgcnxRN
https://ibb.co.com/Jwb9j1YG
https://ibb.co.com/gF6M4gSz
https://ibb.co.com/QF21yFNL
