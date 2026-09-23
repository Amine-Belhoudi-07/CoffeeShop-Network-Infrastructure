# Network Testing

Network testing was performed on the CoffeeShop network using Cisco Packet Tracer to verify the correctness of the configuration and connectivity between different networks.

## 1. VLAN Testing

# Command:

"""cisco
show vlan brief
"""

# Result: PASS

The following VLANs were verified:

* VLAN 10 - Management / Office
* VLAN 20 - POS
* VLAN 30 - Guest
* VLAN 99 - Network Management

---

## 2. Trunk Testing

# Command:

"""cisco
show interfaces trunk
"""

# Result: PASS

The trunk connection between the Switch and Router was verified, with the following VLANs allowed:

* VLAN 10
* VLAN 20
* VLAN 30
* VLAN 99

---

## 3. Router Interface Testing

# Command:

"""cisco
show ip interface brief
"""

# Result:  PASS

The following router subinterfaces were verified as operational:

| Interface | IP Address   | VLAN |
| --------- | ------------ | ---- |
| G0/1.10   | 192.168.10.1 | 10   |
| G0/1.20   | 192.168.20.1 | 20   |
| G0/1.30   | 192.168.30.1 | 30   |
| G0/1.99   | 192.168.99.1 | 99   |

---

## 4. DHCP Testing

# Result: PASS

DHCP was tested to verify that devices successfully receive IP addresses automatically.

The following networks were used:

* VLAN 10 → 192.168.10.0/24
* VLAN 20 → 192.168.20.0/24
* VLAN 30 → 192.168.30.0/24

---

## 5. Gateway Connectivity

Connectivity to the default gateway of each VLAN was tested.

| VLAN | Gateway      | Result |
| ---- | ------------ | ------ |
| 10   | 192.168.10.1 |  PASS  |
| 20   | 192.168.20.1 |  PASS  |
| 30   | 192.168.30.1 |  PASS  |
| 99   | 192.168.99.1 |  PASS  |

---

## 6. Inter-VLAN Routing

# Result: PASS

Connectivity between devices located in different VLANs was tested successfully.

The results confirm that **Router-on-a-Stick** is working correctly.

---

## 7. Guest VLAN ACL Testing

The ACL configured for Guest VLAN 30 was tested.

| Test                         | Expected | Result |
| ---------------------------- | -------- | ------ |
| Guest → VLAN 10              | Blocked  |  PASS  |
| Guest → VLAN 20              | Blocked  |  PASS  |
| Guest → VLAN 99              | Blocked  |  PASS  |
| Guest → Allowed destinations | Allowed  |  PASS  |

**ACL used:**

"""text
Guest_RESTRICTIONS
"""

---

## 8. ACL Verification

# Command:

"""cisco
show access-lists Guest_RESTRICTIONS
"""

# Result: PASS

The ACL rules responsible for restricting access from the Guest VLAN were verified successfully.

---

## 9. SSH Testing

SSH access to the Switch Management interface was tested.

# Management IP:

"""text
192.168.99.2
"""

# Result: PASS

SSH access to the Switch was successfully verified from the Management network.

---

# Final Result

All network tests were successfully completed.

# Overall Status:  ALL TESTS PASSED
