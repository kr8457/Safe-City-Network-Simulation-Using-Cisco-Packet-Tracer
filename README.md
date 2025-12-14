# SafeCityNetwork – Cisco CN Project

## 📌 Project Overview

**SafeCityNetwork** is a Computer Networks (CN) project that simulates a secure, scalable city-wide network using **Cisco Packet Tracer**. The network is divided into multiple zones (North, South, East, West) representing different city areas such as Police Stations, Hospitals, and Administrative Offices.

The project demonstrates real-world enterprise networking concepts including VLANs, inter-VLAN routing, dynamic routing, DHCP, and network security.

---

## 🎯 Objectives

* Design a multi-zone city network architecture
* Implement VLAN-based logical segmentation
* Enable inter-VLAN routing using multilayer switches
* Configure OSPF for dynamic routing between zones
* Provide centralized DHCP services
* Enhance security using Port Security and IPS

---

## 🗺️ Network Design

* **Base Network:** 192.168.0.0/16
* Network divided into **North, East, South, West Zones** and a **Central Building**
* Each zone uses a dedicated **/24 subnet**
* VLANs are subnetted into **/26 networks** (62 hosts each)
* **/30 subnets** are used for WAN point-to-point links

---

## 📐 Detailed IP Addressing Scheme

### 1️⃣ North Zone – `192.168.10.0/24`

| VLAN | Department          | Subnet            |
| ---- | ------------------- | ----------------- |
| 10   | Police Station      | 192.168.10.0/26   |
| 20   | 1122 Rescue Center  | 192.168.10.64/26  |
| 30   | Checkpoint          | 192.168.10.128/26 |
| –    | Management/Reserved | 192.168.10.192/26 |

### 2️⃣ East Zone – `192.168.20.0/24`

| VLAN | Department          | Subnet            |
| ---- | ------------------- | ----------------- |
| 10   | Police Station      | 192.168.20.0/26   |
| 20   | 1122 Rescue Center  | 192.168.20.64/26  |
| 30   | Checkpoint          | 192.168.20.128/26 |
| –    | Management/Reserved | 192.168.20.192/26 |

### 3️⃣ South Zone – `192.168.30.0/24`

| VLAN | Department          | Subnet            |
| ---- | ------------------- | ----------------- |
| 10   | Police Station      | 192.168.30.0/26   |
| 20   | 1122 Rescue Center  | 192.168.30.64/26  |
| 30   | Checkpoint          | 192.168.30.128/26 |
| –    | Management/Reserved | 192.168.30.192/26 |

### 4️⃣ West Zone – `192.168.40.0/24`

| VLAN | Department          | Subnet            |
| ---- | ------------------- | ----------------- |
| 10   | Police Station      | 192.168.40.0/26   |
| 20   | 1122 Rescue Center  | 192.168.40.64/26  |
| 30   | Checkpoint          | 192.168.40.128/26 |
| –    | Management/Reserved | 192.168.40.192/26 |

### 5️⃣ Central Building – `192.168.50.0/24`

| VLAN | Department   | Subnet            |
| ---- | ------------ | ----------------- |
| 100  | Admin Floor  | 192.168.50.0/26   |
| 200  | Control Room | 192.168.50.64/26  |
| 300  | Data Center  | 192.168.50.128/26 |
| –    | Reserved     | 192.168.50.192/26 |

### 6️⃣ WAN Links – `192.168.100.0/24`

Point-to-point WAN connectivity using **/30 subnets** between:

* Zone Routers ↔ Core Routers (Core1, Core2)
* Core1 ↔ Core2
* Multilayer Switches ↔ Zone Routers

### 7️⃣ Servers (VLAN 300 – Data Center)

| Service | IP Address     |
| ------- | -------------- |
| DNS     | 192.168.50.130 |
| DHCP    | 192.168.50.131 |
| Web     | 192.168.50.135 |
| File    | 192.168.50.145 |
| Mail    | 192.168.50.150 |



## ⚙️ Technologies Used

* Cisco Packet Tracer
* Cisco Routers
* Cisco Multilayer Switches (MLS)
* OSPF (Open Shortest Path First)
* DHCP Server & Relay (ip helper-address)
* Port Security
* Intrusion Prevention System (IPS)

---

## 🔐 Security Features

* **Port Security:** Limits MAC addresses on access ports to prevent unauthorized access
* **IPS:** Configured on edge routers to detect and block malicious traffic

---

## 🧪 Testing & Verification

The network was tested using:

* Ping and PDU tests between VLANs and zones
* Verification commands:

  * `show ip route`
  * `show ip ospf neighbor`
  * `show port-security interface`
  * `show ip ips statistics`

All zones successfully communicate while maintaining logical and secure segmentation.




## 🚀 How to Run the Project

1. Download the `.pkt` file from the `topology` folder
2. Open it in **Cisco Packet Tracer**
3. Use Simulation mode to test connectivity and routing
4. Verify configurations using CLI commands

---





## 📄 License

This project is created for **educational purposes only**.
