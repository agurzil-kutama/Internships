# CCNA Task 1: Build Your Lab & How Networks Work

## 🎯 Objective
Build a foundational Cisco Packet Tracer topology from scratch. The core objective was to establish end-to-end Layer 3 connectivity between two separate LANs using two routers, two switches, and four end-devices (PCs), configured with static routing.

## 🖼️ Topology
![Packet Tracer Topology](./screenshots/topology.png)

## 🛠️ Tools Used
*   **Cisco Packet Tracer** (Network Simulation)
*   **Cisco IOS** (Router & Switch Configuration)

## ⚙️ Methodology & Key Actions
1.  **Topology Design:** Designed a network with two /24 subnets (`192.168.1.0/24` and `192.168.2.0/24`) connected by a point-to-point WAN link.
2.  **Device Configuration:** Assigned IPv4 addresses, subnet masks, and default gateways to all PCs and router interfaces.
3.  **Static Routing:** Configured a static route on each router to enable communication between the two remote subnets.
4.  **Verification:** Used the `ping` and `traceroute` commands from end-devices to verify end-to-end connectivity and path selection.

## 🔍 Critical Analysis & Lessons Learned
*   **TTL Analysis:** I verified that a successful ICMP `ping` from PC1 to PC4 returned a `TTL=126`. A default Windows TTL is 128, and the value decreased by 2, confirming the packet traversed exactly two router hops as designed.
*   **The "Why" of Static Routes:** This lab demonstrated why routers do not automatically know about remote networks. Without a static route, a router will drop a packet destined for a network not directly connected to it, even if there is a physical path.
*   **What I'd Improve:** For a production network, a dynamic routing protocol like OSPF would be used instead of static routes for better scalability and automatic failover. I would also implement port security on the switches to prevent unauthorized devices from connecting.

## 📄 Deliverable
*   📄 [**View Full Detailed Lab Report (PDF)**](./CCNA_Task1_Report.pdf)
