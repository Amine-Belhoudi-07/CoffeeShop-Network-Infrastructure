# IP Addressing Plan

## VLAN 10 - Management / Office

* Network: `192.168.10.0/24`
* Gateway: `192.168.10.1`
* DHCP Range: `192.168.10.21` to `192.168.10.254`
* Reserved Addresses: `192.168.10.1` to `192.168.10.20`

## VLAN 20 - POS

* Network: `192.168.20.0/24`
* Gateway: `192.168.20.1`
* DHCP Range: `192.168.20.21` to `192.168.20.254`
* Reserved Addresses: `192.168.20.1` to `192.168.20.20`

## VLAN 30 - Guest

* Network: `192.168.30.0/24`
* Gateway: `192.168.30.1`
* DHCP Range: `192.168.30.21` to `192.168.30.254`
* Reserved Addresses: `192.168.30.1` to `192.168.30.20`

## VLAN 99 - Network Management

* Network: `192.168.99.0/24`
* Router Gateway: `192.168.99.1`
* Switch Management IP: `192.168.99.2`
