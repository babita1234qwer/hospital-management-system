🏥 Hospital Management Network – VLAN & Router-on-a-Stick Topology

This project demonstrates a hospital network using Router-on-a-Stick (ROAS) and VLAN segmentation.
It includes a centralized Hospital Management System (HMS) Server accessed by different departments.

📌 Devices Used

1 Router (Inter-VLAN routing)

1 Switch (VLAN-enabled)

Doctor PC

Reception PC

HMS Server

🔧 VLAN Design
Department	VLAN ID	Network
Reception	10	192.168.10.0/24
Doctor Dept	20	192.168.20.0/24
HMS Server	30	192.168.30.0/24
📡 Router (ROAS) Configuration
interface GigabitEthernet0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0

interface GigabitEthernet0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0

interface GigabitEthernet0/0.30
 encapsulation dot1Q 30
 ip address 192.168.30.1 255.255.255.0

⚙️ Switch Configuration
Create VLANs
vlan 10
vlan 20
vlan 30

Assign Ports
interface fa0/1
 switchport access vlan 10     (Reception)

interface fa0/2
 switchport access vlan 20     (Doctor)

interface fa0/3
 switchport access vlan 30     (HMS Server)

Trunk Link
interface gig0/1
 switchport mode trunk

🎯 Features

Different departments isolated using VLANs
Inter-VLAN communication via router
HMS Server accessible from all departments
Secure and scalable                                                                                
🏥 Simple Hospital Network – Single LAN Setup

This project represents a basic hospital network where all devices are connected through a single switch without VLANs.

📌 Devices Used

1 Switch

Doctor PC

Reception PC

HMS Server

No router and no VLANs are used in this model.

🌐 IP Addressing Scheme

All devices belong to the same network:

Device	IP Address	Subnet Mask
Doctor PC	192.168.1.10	255.255.255.0
Reception PC	192.168.1.11	255.255.255.0
HMS Server	192.168.1.20	255.255.255.0
🔧 Switch Configuration

No VLANs

Default VLAN 1 is used

All ports are in access mode automatically

No manual switch configuration required.

📝 Features

Very simple layout

All devices communicate directly

HMS Server accessible to both PCs

Good for beginners and basic demonstrations
