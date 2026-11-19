# Three-Tier Hierarchical Campus Network

A redundant three-tier campus network designed, configured, and tested in **Cisco Packet Tracer 9.0**.

## Project status

**Implementation complete. Connectivity and HSRP failover tests reported successful.**

The project demonstrates a hierarchical Core–Distribution–Access design with VLAN segmentation, inter-VLAN routing, HSRP gateway redundancy, Rapid-PVST, DHCP, and static printer addressing.

> **Evidence note:** The specific PC0 connectivity results and two HSRP failover results were supplied in the project conversation. The user subsequently confirmed that the remaining verification was also completed. Detailed CLI output for those additional checks was not supplied here, so it is not reproduced or fabricated in this repository.

## Topology overview

![Three-tier campus network topology](screenshots/topology-overview.png)

### Device inventory

| Layer | Device model | Quantity | Device names |
|---|---|---:|---|
| Core | Cisco Catalyst 3560-24PS | 2 | CORE1, CORE2 |
| Distribution | Cisco Catalyst 3560-24PS | 4 | DSW1–DSW4 |
| Access | Cisco Catalyst 2960-24TT | 4 | ASW1–ASW4 |
| End devices | PC-PT | 8 | PC0–PC7 |
| End devices | Printer-PT | 4 | Printer0–Printer3 |

**Total: 22 devices.**

## Network design and technologies

- Three-tier hierarchical campus network architecture
- VLAN segmentation for users, printers, and switch management
- IEEE 802.1Q trunking between switches
- Inter-VLAN routing on the core multilayer switches
- HSRP virtual default gateways for first-hop redundancy
- Rapid-PVST for Layer 2 loop prevention and redundant-path management
- DHCP address allocation for user PCs
- Static IPv4 addressing for network printers
- Redundant uplinks between core, distribution, and access layers

## VLAN and IP addressing plan

| VLAN | Name | Network | HSRP virtual gateway |
|---:|---|---|---|
| 10 | USERS | `192.168.10.0/24` | `192.168.10.1` |
| 30 | PRINTERS | `192.168.30.0/24` | `192.168.30.1` |
| 99 | MANAGEMENT | `192.168.99.0/24` | `192.168.99.1` |

### HSRP preferred active gateways

| VLAN | Preferred active switch | Virtual IP |
|---:|---|---|
| 10 – USERS | CORE1 | `192.168.10.1` |
| 30 – PRINTERS | CORE2 | `192.168.30.1` |
| 99 – MANAGEMENT | CORE1 | `192.168.99.1` |

### Core switch SVI addresses

| Switch | VLAN 10 | VLAN 30 | VLAN 99 |
|---|---|---|---|
| CORE1 | `192.168.10.2/24` | `192.168.30.2/24` | `192.168.99.2/24` |
| CORE2 | `192.168.10.3/24` | `192.168.30.3/24` | `192.168.99.3/24` |

### Switch management addresses

| Switch | Management IP |
|---|---|
| DSW1 | `192.168.99.11/24` |
| DSW2 | `192.168.99.12/24` |
| DSW3 | `192.168.99.13/24` |
| DSW4 | `192.168.99.14/24` |
| ASW1 | `192.168.99.21/24` |
| ASW2 | `192.168.99.22/24` |
| ASW3 | `192.168.99.23/24` |
| ASW4 | `192.168.99.24/24` |

Management default gateway: `192.168.99.1`.

### End-device addressing

**PCs**

- PC0–PC7 use DHCP.
- DHCP pool is configured on CORE1.
- Available pool range: `192.168.10.21–192.168.10.100`.
- Subnet mask: `255.255.255.0`.
- Default gateway: `192.168.10.1`.
- DNS server: `8.8.8.8`.

**Printers**

| Printer | IP address | Subnet mask | Default gateway |
|---|---|---|---|
| Printer0 | `192.168.30.101` | `255.255.255.0` | `192.168.30.1` |
| Printer1 | `192.168.30.102` | `255.255.255.0` | `192.168.30.1` |
| Printer2 | `192.168.30.103` | `255.255.255.0` | `192.168.30.1` |
| Printer3 | `192.168.30.104` | `255.255.255.0` | `192.168.30.1` |

DNS server: `8.8.8.8`.

## Repository structure

```text
three-tier-campus-network/
├── configs/
│   ├── core/
│   │   ├── CORE1.txt
│   │   └── CORE2.txt
│   ├── distribution/
│   │   ├── DSW1.txt
│   │   ├── DSW2.txt
│   │   ├── DSW3.txt
│   │   └── DSW4.txt
│   └── access/
│       ├── ASW1.txt
│       ├── ASW2.txt
│       ├── ASW3.txt
│       └── ASW4.txt
├── docs/
│   ├── IP_ADDRESSING.md
│   ├── PORT_CONNECTION_MAP.md
│   ├── TESTING_CHECKLIST.md
│   └── TEST_RESULTS.md
├── packet-tracer-project/
│   └── README.md
├── screenshots/
│   └── topology-overview.png
├── .gitignore
├── LINKEDIN_POST_DRAFT.md
└── README.md
```

## Configuration files

The `configs/` directory contains the CLI configuration for all ten switches:

- `configs/core/` – CORE1 and CORE2
- `configs/distribution/` – DSW1, DSW2, DSW3, and DSW4
- `configs/access/` – ASW1, ASW2, ASW3, and ASW4

Read [`docs/PORT_CONNECTION_MAP.md`](docs/PORT_CONNECTION_MAP.md) for the physical interface connections and [`docs/IP_ADDRESSING.md`](docs/IP_ADDRESSING.md) for the complete addressing plan.

## Testing and results

### Reported PC0 connectivity tests

| Test | Result |
|---|---|
| PC0 receives DHCP address | **PASS** |
| PC0 reaches VLAN 10 gateway (`192.168.10.1`) | **PASS** |
| PC0 reaches VLAN 30 gateway (`192.168.30.1`) | **PASS** |
| PC0 reaches Printer0 (`192.168.30.101`) | **PASS** |
| PC0 reaches Printer1 (`192.168.30.102`) | **PASS** |
| PC0 reaches Printer2 (`192.168.30.103`) | **PASS** |
| PC0 reaches Printer3 (`192.168.30.104`) | **PASS** |

**PC0 connectivity: 7/7 reported tests passed.**

### Reported HSRP failover tests

| Failure scenario | Expected failover | Result |
|---|---|---|
| CORE1 VLAN 10 SVI shutdown | CORE2 becomes Active for VLAN 10 | **PASS** |
| CORE2 VLAN 30 SVI shutdown | CORE1 becomes Active for VLAN 30 | **PASS** |

**HSRP failover: 2/2 reported tests passed.**

The tested virtual gateway addresses remained the configured HSRP addresses. The user also confirmed completing the remaining network verification. See [`docs/TEST_RESULTS.md`](docs/TEST_RESULTS.md) for the evidence summary and limitations.

### Useful verification commands

Run on switches:

```cisco
show vlan brief
show interfaces trunk
show ip interface brief
show spanning-tree
show standby brief
show ip route
```

On CORE1:

```cisco
show ip dhcp binding
show ip dhcp pool
```

On PCs:

```text
ipconfig
ping 192.168.10.1
ping 192.168.30.1
ping 192.168.30.101
```

## Important design notes

1. **DHCP server placement:** The DHCP pool is configured on CORE1 only. HSRP provides gateway redundancy, not DHCP server redundancy. If CORE1 is unavailable, existing clients may retain their leases, but new DHCP requests may not receive a lease until DHCP service is available again.
2. **Spanning Tree:** An orange/amber switch port can be a normal alternate or blocking path in a redundant Layer 2 topology. Verify the port state using `show spanning-tree`; do not remove redundant links merely to make every indicator green.
3. **Internet access:** This topology does not include an ISP or Internet edge router. The project demonstrates internal campus connectivity, not external Internet access.
4. **Packet Tracer file:** The native `.pkt` file must be saved from Cisco Packet Tracer on the project owner's computer and added to `packet-tracer-project/`. It is not generated by this documentation package.

## How to reproduce the project

1. Use Cisco Packet Tracer 9.0.
2. Add the devices listed in the inventory.
3. Connect the devices according to [`docs/PORT_CONNECTION_MAP.md`](docs/PORT_CONNECTION_MAP.md).
4. Apply the matching switch configuration from `configs/`.
5. Configure PCs for DHCP.
6. Configure printer static IP addresses according to `docs/IP_ADDRESSING.md`.
7. Run the tests in `docs/TESTING_CHECKLIST.md`.
8. Save the native Packet Tracer project as `three-tier-campus-network.pkt` in `packet-tracer-project/`.

## Project learning outcomes

This project provided practical experience with:

- Hierarchical network design
- VLAN planning and segmentation
- Layer 2 trunking
- Inter-VLAN routing
- HSRP first-hop redundancy
- Rapid-PVST and redundant Layer 2 paths
- DHCP and static IP addressing
- Network connectivity testing and troubleshooting
- Technical documentation and portfolio preparation

---

**Platform:** Cisco Packet Tracer 9.0  
**Project type:** Three-tier hierarchical campus network  
**Status:** Implementation complete; reported connectivity and HSRP failover tests passed.
