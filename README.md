# Enterprise-Network-Design
Multi-branch enterprise network using OSPF and HSRP (Cisco Packet Tracer)
# Enterprise Company Network Design

## 📌 Project Overview

This project presents the **design and implementation of a secure, scalable, and fault-tolerant enterprise company network** using industry-standard networking concepts. The network connects a **Head Office (HQ)** with multiple **Branch Offices** and ensures **high availability, dynamic routing, redundancy, and security**.

The project is designed and simulated using **Cisco Packet Tracer** and reflects a **real-world enterprise network architecture** suitable for medium-to-large organizations.

---

## 🎯 Objectives

* Design a **multi-branch enterprise network**
* Implement **dynamic routing (OSPF – Area 0)**
* Provide **gateway redundancy using HSRP**
* Ensure **fault tolerance and fast failover**
* Apply **network security best practices**
* Create a **scalable IP addressing scheme**

---

## 🏢 Network Topology

### 1. Head Office (HQ)

* Core Layer Routers (2x for redundancy)
* Distribution Switch
* Access Switches
* Servers (DNS, DHCP, Web)
* Internet Gateway

### 2. Branch Offices (Branch A, Branch B, Branch C)

* Two routers per branch (HSRP)
* One Layer-2 Access Switch
* End Devices (PCs, Printers)

### 3. WAN Connectivity

* Point-to-Point Serial Links
* /30 IP addressing for WAN links

---

## 🧠 Technologies Used

| Technology               | Purpose                 |
| ------------------------ | ----------------------- |
| OSPF (Area 0)            | Dynamic routing         |
| HSRP                     | Gateway redundancy      |
| DHCP                     | Automatic IP assignment |
| Static + Dynamic Routing | Hybrid routing approach |

---

## 🌐 IP Addressing Scheme

### LAN Networks

* Each LAN uses **/24 subnet**

| Location | Network      | Subnet Mask |
| -------- | ------------ | ----------- |
| Branch A  | 192.168.10.0 | /24         |
| Branch B | 192.168.20.0 | /24         |
| Branch C | 192.168.30.0 | /24         |

### WAN Links

* /30 subnets

Example:

* 10.0.0.0/30
* 10.0.0.4/30

---

## 🔁 Routing Protocol – OSPF

* Single Area: **Area 0**
* All routers participate in OSPF
* Automatic route learning
* Fast convergence during link failure

Example Configuration:

```
router ospf 1
 network 192.168.0.0 0.0.255.255 area 0
 network 10.0.0.0 0.0.0.255 area 0
```

---

## 🛡️ Gateway Redundancy – HSRP

* Implemented on each branch
* Provides virtual gateway IP
* Failover time: **3–10 seconds**

Example:

```
interface g0/0
 standby 1 ip 192.168.20.1
 standby 1 priority 110
 standby 1 preempt

## 🧪 Testing & Verification

* Router failure test
* Link failure simulation
* End-to-end connectivity tests (ping, traceroute)
* HSRP failover verification
* OSPF neighbor adjacency verification

## 🛠 Tools Used

* Cisco Packet Tracer
* Windows 10
* GitHub (Version Control)

---

## 📦 Project Files

This project is uploaded as a single ZIP file.

➡️ Download **Enterprise-Network-Design.zip**  
➡️ Extract it to access:
- Cisco Packet Tracer (.pkt) file
- Router configuration files
- Network topology diagram

---

## 🚀 Future Enhancements

* VLAN inter-routing using Layer-3 switches
* NAT and Internet simulation
* Firewall integration
* Network monitoring (SNMP)

---

## 👨‍💻 Author

**Muhammad Fawad**
Bachelor of Computer Engineering
Bahria University Islamabad

---

## 📜 License

This project is for **educational purposes** only.
