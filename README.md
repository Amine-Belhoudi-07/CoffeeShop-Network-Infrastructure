# CoffeeShop-Network-Infrastructure

A network design and implementation project for a coffee shop using Cisco Packet Tracer.

##  Project Objectives

* Segment the network using VLANs
* Implement Router-on-a-Stick
* Configure DHCP
* Configure SSH
* Implement ACLs
* Isolate the Guest network
* Test connectivity between different networks

##  Technologies Used

* Cisco Packet Tracer
* VLAN
* 802.1Q
* Router-on-a-Stick
* Inter-VLAN Routing
* DHCP
* SSH
* Extended ACL
* TCP/IP

##  VLANs

| VLAN | Network         | Purpose             |
| ---- | --------------- | ------------------- |
| 10   | 192.168.10.0/24 | Management / Office |
| 20   | 192.168.20.0/24 | POS                 |
| 30   | 192.168.30.0/24 | Guest               |
| 99   | 192.168.99.0/24 | Network Management  |

##  Router-on-a-Stick

Router-on-a-Stick was implemented using the following subinterfaces:

* "G0/1.10" → "192.168.10.1"
* "G0/1.20" → "192.168.20.1"
* "G0/1.30" → "192.168.30.1"
* "G0/1.99" → "192.168.99.1"

##  DHCP

DHCP was configured for the following VLANs:

* VLAN 10
* VLAN 20
* VLAN 30

IP addresses from ".1" to ".20" were reserved for network infrastructure and static assignments.

##  ACL

The following ACL was created:

"""
Guest_RESTRICTIONS
"""

It is used to restrict access from Guest VLAN 30.

Guest VLAN 30 is denied access to:

* VLAN 10
* VLAN 20
* VLAN 99

##  Network Testing

The following tests were performed:

* DHCP testing
* Gateway connectivity
* Inter-VLAN connectivity
* ACL restrictions
* SSH connectivity

All configured network tests were successfully completed.


