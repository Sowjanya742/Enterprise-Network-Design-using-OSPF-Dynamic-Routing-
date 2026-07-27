# 🌐 Enterprise Multi-Site Network using Cisco Packet Tracer

![Cisco](https://img.shields.io/badge/Cisco-Packet%20Tracer-blue)
![OSPF](https://img.shields.io/badge/Routing-OSPF-success)
![VLAN](https://img.shields.io/badge/VLAN-802.1Q-orange)
![DHCP](https://img.shields.io/badge/DHCP-Centralized-green)
![Status](https://img.shields.io/badge/Project-In%20Progress-yellow)

## 📌 Project Overview

This project demonstrates the design and implementation of a secure multi-site enterprise network using Cisco Packet Tracer.

The network connects a Headquarters (Core Site) and a Branch Office through dynamic routing using OSPF. Multiple VLANs are deployed to logically separate departments, while centralized DHCP provides automatic IP address allocation across remote networks using DHCP Relay (IP Helper).

The project simulates real-world enterprise networking concepts including Layer-2 switching, Layer-3 routing, Router-on-a-Stick, VLAN segmentation, centralized DHCP, management VLANs, and WAN connectivity.

Future enhancements include Internet connectivity using NAT/PAT and traffic filtering using Standard and Extended ACLs.

---

# 🖥️ Network Topology

> **Topology Screenshot**

```
docs/01-topology.png
```

The topology contains:

- Internet Router
- ISP Router
- Company Edge Router
- Core Router (Head Office)
- Branch Router
- HR Access Switch
- Branch Access Switch
- DHCP Server
- Multiple PCs and Laptops

---

# 🛠 Technologies Used

- Cisco Packet Tracer 9.x
- Cisco 2911 Routers
- Cisco Catalyst 2960 Switches
- IPv4 Addressing
- VLANs
- IEEE 802.1Q Trunking
- Router-on-a-Stick
- OSPF (Area 0)
- DHCP Relay (IP Helper)
- Centralized DHCP Server
- Static Default Route
- Management VLAN

**Planned**

- NAT
- PAT
- Standard ACL
- Extended ACL

---

# 🏢 Network Architecture

The enterprise network consists of two sites:

## Headquarters

- HR Department (VLAN 10)
- Server VLAN (VLAN 40)
- Management VLAN (VLAN 60)

## Branch Office

- Branch Desk (VLAN 20)
- Trainees (VLAN 30)
- Management VLAN (VLAN 50)

Communication between all VLANs is performed using Router-on-a-Stick.

Both sites exchange routing information dynamically using OSPF Area 0.

---

# 🌍 IP Addressing Plan

| Network | Purpose | Gateway |
|----------|----------|----------|
|10.16.1.0/29|HR VLAN|10.16.1.1|
|172.16.1.0/29|Branch Desk|172.16.1.1|
|192.168.1.0/29|Trainees|192.168.1.1|
|192.168.40.0/24|Server VLAN|192.168.40.1|
|192.168.50.0/24|Branch Management|192.168.50.1|
|192.168.60.0/24|Core Management|192.168.60.1|
|192.168.10.0/30|Core ↔ Branch Link|-|
|10.0.0.0/30|Edge ↔ Core Link|-|
|2.2.2.0/30|ISP ↔ Edge|-|
|1.1.1.0/30|Internet ↔ ISP|-|

---

# 🏷 VLAN Design

| VLAN | Name | Network |
|------|------|----------|
|10|HR|10.16.1.0/29|
|20|Branch Desk|172.16.1.0/29|
|30|Trainees|192.168.1.0/29|
|40|Servers|192.168.40.0/24|
|50|Branch Management|192.168.50.0/24|
|60|Core Management|192.168.60.0/24|

Features

- VLAN Segmentation
- Access Ports
- 802.1Q Trunk Links
- Router-on-a-Stick

---

# 🔀 OSPF Configuration

Dynamic routing is implemented using OSPF Area 0.

### Participating Routers

- Core Router
- Branch Router
- Edge Router

### Features

- Automatic Route Advertisement
- Dynamic Route Learning
- End-to-End Reachability
- Multi-router Enterprise Topology

Verification

```
show ip ospf neighbor

show ip route

show ip protocols
```

---

# 📡 DHCP Architecture

A centralized DHCP Server is deployed in VLAN 40.

Remote VLANs obtain IP addresses using DHCP Relay (IP Helper).

Configured DHCP Pools

| VLAN | DHCP Pool |
|------|-----------|
|VLAN10|10.16.1.2 - 10.16.1.6|
|VLAN20|172.16.1.2 - 172.16.1.6|
|VLAN30|192.168.1.2 - 192.168.1.6|

DHCP Process

```
Client

↓

DHCP Discover

↓

Router (IP Helper)

↓

DHCP Server

↓

Offer

↓

Request

↓

ACK

↓

Client Receives IP
```

Verification

```
ipconfig

show ip interface

show ip dhcp binding
```

---

# 🌐 NAT / PAT Configuration

**Status:** 🚧 Planned

The Edge Router will perform Network Address Translation (NAT) to allow internal private IP addresses to communicate with external public networks.

### Planned Features

- Static NAT
- Dynamic NAT
- PAT (NAT Overload)
- Internet Connectivity

Verification

```
show ip nat translations

show ip nat statistics
```

---

# 🔒 ACL Implementation

**Status:** 🚧 Planned

Security will be implemented using both Standard and Extended Access Control Lists.

### Planned Policies

- Restrict unauthorized VLAN access
- Secure Management VLAN
- Control inter-VLAN communication
- Allow Internet while restricting sensitive resources

Verification

```
show access-lists

show running-config

show ip interface
```

---

# ✅ Verification Commands

### OSPF

```
show ip ospf neighbor

show ip route
```

### DHCP

```
ipconfig

show ip dhcp binding
```

### NAT

```
show ip nat translations

show ip nat statistics
```

### ACL

```
show access-lists
```

### Connectivity

```
ping

traceroute
```

---

# 📦 Packet Flow

The project verifies the following traffic flows:

✅ DHCP Discover

✅ DHCP Offer

✅ DHCP Request

✅ DHCP ACK

✅ ARP Resolution

✅ ICMP Ping

✅ OSPF Hello

✅ Dynamic Route Advertisement

Future

⬜ NAT Translation

⬜ ACL Filtering

---

# 📷 Project Screenshots

```
Screenshots/

01-topology.png


```

---

# 🚀 Future Improvements

- Configure Static NAT
- Configure Dynamic NAT
- Configure PAT
- Implement Standard ACL
- Implement Extended ACL
- Enable Internet Connectivity
- Configure SSH Remote Management
- Configure Syslog Server
- Configure NTP
- Configure SNMP Monitoring

---

# 📚 Concepts Covered

- Enterprise Network Design
- IPv4 Addressing
- Subnetting
- VLANs
- Access & Trunk Ports
- Router-on-a-Stick
- Inter-VLAN Routing
- OSPF
- Centralized DHCP
- DHCP Relay
- Management VLAN
- Static Routing
- WAN Connectivity
- NAT (Planned)
- PAT (Planned)
- Standard ACL (Planned)
- Extended ACL (Planned)

---

# 👨‍💻 Author

**Sowjanya Peeka**

Aspiring Network Engineer

### Skills

- Cisco Routing & Switching
- OSPF
- VLAN
- Inter-VLAN Routing
- DHCP
- NAT
- ACL
- Troubleshooting
- Cisco Packet Tracer

---

⭐ If you found this project useful, feel free to star the repository.
