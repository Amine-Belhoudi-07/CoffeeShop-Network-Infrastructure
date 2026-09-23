# Network Design

## Architecture

The CoffeeShop network uses a Router-on-a-Stick architecture.

The Cisco 2911 router provides:

* Inter-VLAN routing
* Default gateways
* DHCP services
* Guest network ACL restrictions

The Cisco switch provides:

* VLAN segmentation
* Access ports
* 802.1Q trunking
* Network management
* SSH management access

## Router

Device name:

`CoffeeShop-RW`

Model:

"Cisco 2911"

## Switch

Device name:

"Coffe-SW"

Model:

"Cisco 3560-24PS"

## Trunk Connection

The connection between the router and switch uses an 802.1Q trunk.

Switch interface:

"Fa0/1"

Allowed VLANs:

* VLAN 10
* VLAN 20
* VLAN 30
* VLAN 99

## Router Subinterfaces

| Interface | VLAN | IP Address   |
| --------- | ---: | ------------ |
| G0/1.10   |   10 | 192.168.10.1 |
| G0/1.20   |   20 | 192.168.20.1 |
| G0/1.30   |   30 | 192.168.30.1 |
| G0/1.99   |   99 | 192.168.99.1 |

## Network Segmentation

The network separates office, POS, guest, and network-management traffic into different VLANs.

The Guest network is restricted from accessing the Management, POS, and Network Management networks using an extended ACL.

## DHCP

The router provides DHCP services for:

* VLAN 10
* VLAN 20
* VLAN 30

VLAN 99 uses a static management IP for the switch.

## Management

The switch is managed through VLAN 99.

Switch management address:

"192.168.99.2"

Router gateway:

"192.168.99.1"

SSH version 2 is configured for remote management.
