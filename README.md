XYZ Company Branch Network Design
This project involves the design and implementation of the network for XYZ Company's branch in Bonalbo, Eastern Australia. The network needs to operate independently from the headquarters and should meet several specified requirements. The network will be designed using Cisco devices (router, switch) and will be configured to ensure secure and efficient communication between departments.

Project Overview
XYZ Company is a fast-growing company with more than 2 million customers globally, focusing on buying and selling food items. The company is opening a branch in Bonalbo, and this network design will ensure smooth communication within the branch. The design includes configuring VLANs, DHCP, and WiFi networks for seamless operation.

Network Requirements:
One Router and One Switch to be used (both Cisco products).
Three Departments:
Admin/IT
Finance/HR
Customer Service/Reception
Each department is assigned to a separate VLAN.
Each department should have a wireless network for users.
Devices in all departments must be able to communicate with each other.
IPv4 addresses should be obtained automatically via DHCP.
IP Addressing:
The network provided by the ISP is 192.168.1.0/24. Based on this, we will allocate subnets for each department and configure VLANs accordingly.
Network Design
1. Router and Switch Configuration:
Router: The router will be used to route traffic between VLANs and handle inter-network communication.
Switch: The switch will handle VLAN assignments, with each department connected to its own VLAN.
2. VLAN Configuration:
We will create separate VLANs for each department to ensure logical separation:

Admin/IT: VLAN 10 (192.168.1.0/26)
Finance/HR: VLAN 20 (192.168.1.64/26)
Customer Service/Reception: VLAN 30 (192.168.1.128/26)
3. DHCP Configuration:
To simplify IP address management, we will configure the router to provide DHCP services. The router will assign dynamic IP addresses within the specific subnets for each VLAN:

VLAN 10 (Admin/IT): 192.168.1.1 - 192.168.1.62
VLAN 20 (Finance/HR): 192.168.1.65 - 192.168.1.126
VLAN 30 (Customer Service/Reception): 192.168.1.129 - 192.168.1.190
4. Wireless Network:
Each department will have a wireless access point connected to the switch. The wireless network will provide connectivity to laptops, mobile phones, and other wireless devices within each department. Each department will have its own WiFi network to ensure proper separation and security.

5. Inter-department Communication:
The router will facilitate communication between different VLANs, allowing devices in each department to communicate with devices in other departments while maintaining logical separation through VLANs.
6. Cable and Hardware Setup:
Ethernet Cables: Used to connect the router, switch, and devices (PCs, printers, etc.).
WiFi Access Points: One per department to provide wireless coverage.
Detailed Configuration
1. Router Configuration:
The router will be configured to handle the routing between VLANs, assign IP addresses via DHCP, and enable the necessary interfaces for communication.

Router IP Configuration:

Interface for VLAN 10: 192.168.1.1
Interface for VLAN 20: 192.168.1.65
Interface for VLAN 30: 192.168.1.129
DHCP Configuration Example (for VLAN 10):

bash
Copy
Edit
ip dhcp pool VLAN10
   network 192.168.1.0 255.255.255.192
   default-router 192.168.1.1
   lease 7
Repeat similar configuration for VLAN 20 and VLAN 30.

2. Switch Configuration:
The switch will be configured to allow VLANs and connect the appropriate devices to the correct VLANs.
VLAN 10 for Admin/IT, VLAN 20 for Finance/HR, and VLAN 30 for Customer Service/Reception.
Example switch configuration:

bash
Copy
Edit
vlan 10
   name Admin_IT
vlan 20
   name Finance_HR
vlan 30
   name Customer_Service

interface fastethernet 0/1
   switchport mode access
   switchport access vlan 10

interface fastethernet 0/2
   switchport mode access
   switchport access vlan 20

interface fastethernet 0/3
   switchport mode access
   switchport access vlan 30
3. Wireless Access Points Configuration:
Each department will have a wireless access point configured with a unique SSID and security settings (e.g., WPA2).

Testing and Validation
Once the network is set up:

Ping Tests: Test connectivity between devices in different VLANs (using the router for inter-VLAN routing).
DHCP Test: Ensure that all devices are receiving an IP address from the router’s DHCP pool.
WiFi Connectivity: Verify that laptops and phones can connect to the wireless network and access internal resources.
VLAN Communication: Ensure devices in each department can communicate with devices in the same VLAN and access shared resources (e.g., printers, servers).
Conclusion
This network design will ensure efficient and secure communication between departments in XYZ Company's Bonalbo branch. By segmenting the network into VLANs, providing wireless access, and configuring DHCP for automatic IP addressing, the network will be both scalable and easy to manage.

Project Files
The project files are available in the repository:

Network Design File: xyz_company_network.pkt – Cisco Packet Tracer file containing the network topology and configurations.
Author Information
Name: Biswajit Sahoo
LinkedIn: Biswajit Sahoo LinkedIn
Email: biswajitsahoo152001@gmail.com
