# Enterprise Multi-Site Network Infrastructure using Cisco Packet Tracer

![Cisco](https://img.shields.io/badge/Cisco-Packet%20Tracer-blue)
![Routing](https://img.shields.io/badge/OSPF-Area%200-green)
![Switching](https://img.shields.io/badge/VLAN-802.1Q-orange)
![NAT](https://img.shields.io/badge/NAT-PAT-red)
![Status](https://img.shields.io/badge/Project-Completed-success)

---

# Project Overview

This project demonstrates the design and implementation of a multi-site enterprise network using Cisco Packet Tracer.

The network consists of a Head Office and a Branch Office connected through a WAN. Internal communication is achieved using OSPF dynamic routing, while Internet connectivity is provided through an Edge Router configured with NAT/PAT.

The project also implements VLAN segmentation, Router-on-a-Stick Inter-VLAN Routing, Centralized DHCP with DHCP Relay, Switch Management VLANs, and Static Default Routing for external connectivity.

---

# Network Topology

Topology Screenshot

```
Screenshots/
└── 01-Topology.png
```

---

# Network Architecture

```
                     Internet
                         │
                  Internet Router
                         │
                     ISP Router
                         │
                    Edge Router
                    (NAT / PAT)
                         │
                    Core Router
                  OSPF Area 0 Backbone
                   │               │
                   │               │
            HR Access Switch   Branch Router
                   │               │
            VLAN10 VLAN40     VLAN20 VLAN30
```

---

# Technologies Used

- Cisco Packet Tracer
- Cisco IOS
- IPv4 Addressing
- VLAN Segmentation
- IEEE 802.1Q Trunking
- Router-on-a-Stick
- Inter-VLAN Routing
- OSPF (Area 0)
- Static Default Route
- DHCP Server
- DHCP Relay (IP Helper Address)
- NAT
- PAT (Overload)
- Layer 2 Switching
- Layer 3 Routing

---

# VLAN Design

| VLAN | Purpose | Network |
|------|---------|----------------|
| VLAN 10 | HR Department | 10.16.1.0/29 |
| VLAN 20 | Branch Users | 172.16.1.0/29 |
| VLAN 30 | Trainee Users | 192.168.1.0/29 |
| VLAN 40 | DHCP Server | 192.168.40.0/24 |
| VLAN 50 | Branch Switch Management | 192.168.50.0/24 |
| VLAN 60 | HR Switch Management | 192.168.60.0/24 |

---

# Implemented Features

- VLAN Segmentation
- IEEE 802.1Q Trunking
- Router-on-a-Stick Inter-VLAN Routing
- OSPF Dynamic Routing (Area 0)
- Static Default Routing
- Dedicated DHCP Server
- DHCP Relay using IP Helper Address
- Switch Management VLANs
- NAT
- PAT (NAT Overload)
- Internet Connectivity
- End-to-End Connectivity Verification

---

# Routing Design

## Internal Network

- OSPF Area 0
- Dynamic Route Advertisement
- Neighbor Adjacency
- Automatic Route Learning

## External Network

- Static Default Route
- Internet access through Edge Router
- NAT/PAT configured on Edge Router

---

# DHCP Implementation

A dedicated DHCP Server is deployed in VLAN 40.

DHCP pools are configured for:

- VLAN 10
- VLAN 20
- VLAN 30

Routers forward DHCP requests using:

```
ip helper-address
```

---

# NAT / PAT

The Edge Router performs NAT Overload (PAT) to allow all internal networks to access external networks using a single public IP address.

Configured Features:

- Inside Interface
- Outside Interface
- Standard ACL
- NAT Overload

---

# Switch Management

Dedicated Management VLANs are configured for both switches.

| Switch | Management VLAN |
|---------|-----------------|
| HR Access Switch | VLAN 60 |
| Branch Switch | VLAN 50 |

---

# Project Structure

```
Enterprise-Multi-Site-Network/

│
├── README.md
│
├── Config/
│   ├── Branch-Router-configuration.txt
│   ├── Branch-SW-config.txt
│   ├── Core-Router-configuration.txt
│   ├── Edge-Router-configuration.txt
│   ├── HR-Access-SW-config.txt
│   ├── ISP-configuration.txt
│   └── Internet-configuration.txt
│
├── Documentation/
│   └── Project Report
│
├── Packet Tracer/
│   └── Enterprise Network Implementation.pkt
│
└── Screenshots/
    ├── 01-Topology.png
    ├── 02-IP-Addressing-Plan.png
    ├── 03-DHCP-Pools.png
    ├── 03-DHCP-Server.png
    ├── 04-DHCP-Client.png
    ├── 05-OSPF-Neighbors.png
    ├── 06-OSPF-Database.png
    ├── 08-NAT-Configuration.png
    ├── 09-NAT-Translations.png
    ├── 10-NAT-Statistics.png
    ├── 11-Ping-Test.png
    ├── 12-Traceroute.png
    └── 13-Internet-connectivity.png

```

---

# Verification Performed

The following features were successfully verified:

- VLAN Communication
- Inter-VLAN Routing
- DHCP Address Assignment
- DHCP Relay Operation
- OSPF Neighbor Formation
- OSPF Database Exchange
- Dynamic Route Learning
- NAT Configuration
- NAT Translation Table
- PAT Operation
- End-to-End Ping Connectivity
- Internet Reachability using Traceroute

---

# Skills Demonstrated

- Enterprise Network Design
- Cisco Routing and Switching
- VLAN Configuration
- IEEE 802.1Q Trunking
- Router-on-a-Stick
- OSPF Routing
- Static Routing
- DHCP Configuration
- DHCP Relay
- NAT
- PAT
- Cisco IOS Configuration
- Network Verification
- Network Troubleshooting

---

# Author

**Sowjanya Peeka**

Aspiring Network Engineer

CCNA Self-Learner

Interested in Enterprise Networking, Routing & Switching, and Network Infrastructure.

---

If you found this project helpful, consider giving it a ⭐ on GitHub.
