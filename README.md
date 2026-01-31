# Enterprise-Network-Project
A complete enterprise network simulation using EVE-NG with OSPF, VRRP, and Security Hardening
## 📌 Project Overview
This project simulates a real-world enterprise network architecture connecting a Headquarters (HQ) with a remote Branch via a simulated ISP using **EVE-NG**. The design focuses on High Availability (HA), Security Hardening, and Scalable Routing.

## 🗺️ Network Topology
![Enterprise Network Topology](images/topology.png)


## 🛠️ Key Technologies Implemented
### 🔹 Switching & Layer 2
- **VLANs & Trunking:** Segmentation of traffic (IT, HR, Sales, VoIP, CCTV).
- **EtherChannel (LACP):** Bundling links between Core switches for bandwidth and redundancy.
- **Port Security:** Restricting access on Access Layer switches.

### 🔹 Routing & Layer 3
- **OSPF Multi-Area:** Area 0 for HQ Backbone and Area 1 for Branch.
- **VRRP:** Providing Gateway Redundancy for VLANs.
- **NAT (PAT):** Overloading internal IPs to a public IP for ISP access.
- **DHCP Relay:** Centralized DHCP management for remote branches.

### 🔒 Security Hardening
- **Infrastructure ACLs:** Extended ACLs to isolate Management VLAN and protect DHCP servers.
- **SSH Hardening:** Restricting management access to specific admin subnets.
- **Zone Separation:** Strict traffic rules between User VLANs and Server Farm.

## 📂 Repository Structure
- `configs/`: Contains the running-config for all Cisco devices (IOS).
- `images/`: High-resolution topology diagrams.

### ⚙️ Performance & Optimization
- **Routing Efficiency:** Used **Passive Interfaces** to minimize OSPF overhead on user subnets.
- **Core Architecture:** Established **Layer 3 Point-to-Point links** (Transit VLANs) for robust Core-to-Core communication.
- **Loop Prevention:** Enabled **RPVST+** across all switches to prevent Layer 2 loops.
- 
## 🚀 How to Run
1. Import the node images in EVE-NG (Cisco IOL or VIOS).
2. Replicate the topology as shown in the diagram.
3. Apply the configurations from the `configs/` folder to the respective devices.

---
**Author:** Abdulhamed.H

**Tools Used:** EVE-NG, Cisco IOS
