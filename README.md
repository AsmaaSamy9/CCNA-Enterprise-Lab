
# Secure Multi-Site Enterprise Network Lab (HQ + Branches)

This project simulates a production-grade enterprise network connecting one Headquarters and two Branch sites using secure encrypted WAN technologies (GRE over IPSec with ISAKMP).

The lab mirrors real enterprise design principles including routing, switching, security, and centralized services delivery.

---

## 🎯 Objectives

- Build scalable & secure enterprise WAN
- Implement multi-layer switching (Core–Distribution–Access)
- Establish secure site-to-site GRE tunnels over IPSec
- Centralize key services at HQ (DHCP, routing, NAT)
- Validate routing, tunneling, and LAN services end-to-end

---

## 🏗️ Network Topology

**Key Components**
- 1× HQ Site (Core, Distribution, Access layers)
- 2× Branch Sites
- GRE tunnels secured with IPSec (ISAKMP/IKE)
- VLAN-segmented LAN design
- LACP EtherChannel uplinks
- HQ acts as DHCP & NAT gateway

> Designed & deployed in **GNS3** using **Cisco IOS**

---

## 🌐 WAN & Tunnel IP Scheme

| Site Link | Public IPs | Tunnel IPs |
|---|---|---|
HQ ↔ Branch1 | HQ: 203.0.13.1/30 <br> B1: 203.0.14.1/30 | HQ Tunnel: 10.0.0.1/30 <br> B1 Tunnel: 10.0.0.2/30 |
HQ ↔ Branch2 | HQ: 203.0.13.1/30 <br> B2: 203.0.15.1/30 | HQ Tunnel: 20.0.0.1/30 <br> B2 Tunnel: 20.0.0.2/30 |

> Each branch uses a dedicated GRE tunnel to HQ, protected with IPSec.

---

## 🧬 Technologies Used

| Category | Technology |
|---|---|
Routing | OSPF Multi-Area (Area 0 / Area 10) |
VPN | GRE over IPSec (ISAKMP / IKE) |
Switching | VLANs, VTPv2, LACP / EtherChannel |
Security | IPSec, ACLs, NAT Exemption |
Services | DHCP, NAT, Inter-VLAN Routing |
Platform | GNS3 + Cisco IOS |

---

## 📌 IP & VLAN Structure (LAN)

| Segment | Subnet |
|---|---|
HQ VLAN10 – Users | 192.168.10.0/24 |
HQ VLAN30 – Mgmt | 192.168.30.0/24 |
HQ VLAN40 – Wireless | 192.168.40.0/24 |
HQ VLAN50 – Servers | 192.168.50.0/24 |
HQ Native VLAN | 999 |
Branch1 LAN | 172.16.2.0/24 |
Branch2 LAN | 172.16.3.0/24 |

---

## 🔐 Security Highlights

- GRE tunnels encrypted with IPSec
- ISAKMP (IKE) for secure negotiation
- NAT exemption for tunnel subnets
- VLAN security hardening (non-default native VLAN)

---

## 🧪 Validation & Testing

| Test | Result |
|---|---|
HQ ↔ Branch Connectivity | ✅ |
Inter-VLAN Routing | ✅ |
GRE + IPSec Tunnel Encryption | ✅ |
OSPF Neighbor Relationships | ✅ |

### Key Verification Commands

```bash
show ip ospf neighbor
show ip route
show interfaces trunk
show etherchannel summary
show crypto isakmp sa
show crypto ipsec sa
````

---

## 📂 Repository Structure

```
CCNA-Enterprise-Lab/
 ├── Diagrams/
 ├── Configs/
 ├── README.md
 └── Results/
     ├── ospf-neighbors.png
     └── ipsec-status.png
```

---

## 👩‍💻 Author

**Asmaa — Presales & Network Engineer**
Building secure, scalable enterprise networks & modern IT infrastructure.
Focused on Cisco, Security, Cloud & advanced routing.

---

## ⭐ Support

If you like this project:

* ⭐ Star this repository
* 🧠 Keep studying, simulating, and breaking things (then fixing them)
  
```

