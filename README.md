# Secure Multi-Site Enterprise Network Lab (HQ + Branches)

This project simulates a production-grade enterprise network connecting one Headquarters and two Branch sites using secure encrypted WAN technologies.

The design follows real-world enterprise standards including routing, switching, security, and centralized services delivery.

---

## 🎯 Objectives

- Build scalable & secure enterprise WAN
- Implement multi-layer campus switching model (Core–Distribution–Access)
- Enforce encrypted site-to-site VPN
- Centralize services at HQ (DHCP, routing, NAT)
- Prepare for future SD-WAN / DMVPN upgrade
- Perform enterprise-grade testing & troubleshooting

---

## 🏗️ Network Topology

**Key Components**
- 1× HQ Site (Core, Distribution, Access)
- 2× Branch Sites
- Encrypted WAN over Internet
- VLAN-segmented LAN design
- LACP EtherChannel uplinks
- NAT & DHCP centralized at HQ

> Designed & deployed in **GNS3** using **Cisco IOS**

---

## 🧬 Technologies Used

| Category | Technology |
|---|---|
Routing | OSPF Multi-Area (Area 0 / Area 10) |
VPN | GRE over IPSec (Phase-1 complete) |
Switching | VLANs, VTPv2, LACP / EtherChannel |
Security | IPSec, ACLs, NAT-Exempt |
Services | DHCP, NAT, Inter-VLAN Routing |
Platform | GNS3, Cisco IOS |

---

## 📌 IP & VLAN Structure

| Segment | Subnet |
|---|---|
HQ VLAN10 – Users | 192.168.10.0/24 |
HQ VLAN30 – Mgmt | 192.168.30.0/24 |
HQ VLAN40 – Wireless | 192.168.40.0/24 |
HQ VLAN50 – Servers | 192.168.50.0/24 |
HQ Native VLAN | 999 |
Branch1 LAN | 172.16.2.0/24 |
Branch2 LAN | 172.16.3.0/24 |
Future DMVPN | 172.31.0.0/24 |

---

## 🔐 Security Implementation

- IPSec encryption for GRE tunnels
- NAT exemption for VPN traffic
- Native VLAN changed from default
- SNMP monitoring enabled

---

## 🧪 Validation & Testing

| Test | Status |
|---|---|
HQ ↔ Branch Connectivity | ✅ |
Inter-VLAN Routing | ✅ |
Branch DHCP via HQ | ✅ |
VPN Encryption | ✅ |
SNMP Reachability | ✅ |
OSPF Neighbors | ✅ |

### CLI Verification Commands

```bash
show ip ospf neighbor
show ip route
show interfaces trunk
show etherchannel summary
show crypto isakmp sa
show crypto ipsec sa
show dmvpn   # future upgrade
````

---

## 🚀 Future Enhancements

* DMVPN Phase-1/2/3 upgrade
* Dual-hub redundancy (HQ + DR)
* Syslog + NMS (LibreNMS / Grafana)
* AAA / TACACS+ / RADIUS
* Firewall + IDS/IPS integration (ASA / FortiGate)

---

## 📂 Repo Structure

```
CCNA-Enterprise-Lab/
 ├── Diagrams/
 ├── Configs/   
 ├── README.md
 └── Results/
     ├── ospf-neighbors.png
     └── ipsec-status.png

---

## 👩‍💻 Author

**Asmaa — Presales & Network Engineer**
Building secure, scalable enterprise networks & modern IT infrastructure.
Focused on Cisco, Security, Cloud & SD-WAN evolution.

---

## ⭐ Support

If you like this project, please:

* ⭐ Star this repository
* 🧠 Keep studying & building labs!