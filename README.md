🛰️ RIPv2 Enterprise Network Lab – GNS3
This project demonstrates the implementation of Routing Information Protocol version 2 (RIPv2) in a small enterprise network using GNS3. The goal was to simulate a realistic multi-router topology with LAN users, load balancing, and internet access through a default route.

🔧 Lab Objectives
✅ Implement RIPv2 on all routers.

✅ Achieve end-to-end connectivity across all networks.

✅ Use passive-interface for LAN-side interfaces.

✅ Configure load balancing for efficient route selection.

✅ Use default-information originate on Router 2 (connected to ISP).

🌐 Network Topology
Routers: R1, R2, R3, R4, ISP

LAN Segments:

LAN-1: 192.168.10.0/24

LAN-2: 192.168.20.0/24

WAN Links: 192.168.12.0/24, 23.0/24, 34.0/24, 41.0/24

📸 Refer to the attached screenshot for full topology

🖥️ Devices Used
PCs: PC1, PC2, PC3, PC4 (for end-user simulation)

Switches: For LAN-side connection

GNS3 for virtualization and testing

🛠️ Key Configurations
RIPv2 Setup on Routers
bash
Copy
Edit
router rip
 version 2
 network 192.168.0.0
 passive-interface <LAN interface>
 no auto-summary
Default Route on R2
bash
Copy
Edit
ip route 0.0.0.0 0.0.0.0 <ISP next hop IP>
router rip
 default-information originate
🧪 Verification & Commands
bash
Copy
Edit
show ip protocols
show ip route rip
debug ip rip
show ip int brief
show run | section rip
show ip int brief | exclude unassigned
✅ Ping Tested: PC1 ↔ PC3 – Success!

📚 What I Learned
Dynamic routing concepts using RIPv2

Using passive-interface for security

Default routing for external reachability

Load balancing with equal-cost routes

Real-time debugging and protocol analysis

👨‍💻 About Me
I’m Gangadhar, a Network Engineer with over 4 years of experience in ISP networking and enterprise network setups.
🧑‍🎓 Certifications:

Cisco Certified Network Associate (CCNA)

Juniper Networks Certified Internet Associate (JNCIA)

