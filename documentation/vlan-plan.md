# VLAN Plan

| VLAN | Name               | Network         | Gateway      | Purpose                       |
| ---- | ------------------ | --------------- | ------------ | ----------------------------- |
| 10   | Management-Office  | 192.168.10.0/24 | 192.168.10.1 | Management and office devices |
| 20   | POS                | 192.168.20.0/24 | 192.168.20.1 | Point of Sale devices         |
| 30   | Guest              | 192.168.30.0/24 | 192.168.30.1 | Guest network / Wi-Fi         |
| 99   | Network-Management | 192.168.99.0/24 | 192.168.99.1 | Network device management     |


# Port Assignment

## VLAN 10 - Management
Fa0/2
Fa0/3
Fa0/4
Fa0/5
Fa0/6


## VLAN 20 - POS
Fa0/7
Fa0/8
Fa0/9


## VLAN 30 - Guest
Fa0/10


## VLAN 99 - Network Management
VLAN 99 is used for managing network devices.

The switch management IP is:

192.168.99.2

The router gateway is:

192.168.99.1
