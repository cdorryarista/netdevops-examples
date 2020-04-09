# DC1_FABRIC

## Table of Contents

- [DC1_FABRIC](#dc1fabric )
  - [Fabric Switches and Management IP](#fabric-switches-and-management-ip)
  - [Fabric Topology](#fabric-topology)
  - [Fabric IP Allocation](#fabric-ip-allocation)
    - [Fabric Point-To-Point Links](#fabric-point-to-point-links)
    - [Point-To-Point Links Node Allocation](#point-to-point-links-node-allocation)
    - [Overlay Loopback Interfaces (BGP EVPN Peering)](#overlay-loopback-interfaces-bgp-evpn-peering)
    - [Loopback0 Interfaces Node Allocation](#loopback0-interfaces-node-allocation)
    - [VTEP Loopback VXLAN Tunnel Source Interfaces (Leafs Only)](#vtep-loopback-vxlan-tunnel-source-interfaces-leafs-only)
    - [VTEP Loopback Node allocation](#vtep-loopback-node-allocation)

## Fabric Switches and Management IP

| Node | Management IP | Platform |
| ---- | ------------- | -------- |
| DC1-SPINE1 | 192.168.100.1/24 | vEOS-LAB |
| DC1-SPINE2 | 192.168.100.2/24 | vEOS-LAB |
| DC1-LEAF1A | 192.168.100.3/24 | vEOS-LAB |
| DC1-LEAF1B | 192.168.100.4/24 | vEOS-LAB |
| DC1-LEAF2A | 192.168.100.5/24 | vEOS-LAB |
| DC1-LEAF2B | 192.168.100.6/24 | vEOS-LAB |
| DC1-LEAF3A | 192.168.100.7/24 | vEOS-LAB |
| DC1-LEAF3B | 192.168.100.8/24 | vEOS-LAB |

## Fabric Topology

| Type | Leaf Node | Leaf Interface | Peer Node | Peer Interface |
| ---- | --------- | -------------- | --------- | -------------- |
| L3 Leaf | DC1-LEAF1A | Ethernet1 | DC1-SPINE1 | Ethernet1 |
| L3 Leaf | DC1-LEAF1A | Ethernet2 | DC1-SPINE2 | Ethernet1 |
| L3 Leaf | DC1-LEAF1B | Ethernet1 | DC1-SPINE1 | Ethernet2 |
| L3 Leaf | DC1-LEAF1B | Ethernet2 | DC1-SPINE2 | Ethernet2 |
| L3 Leaf | DC1-LEAF2A | Ethernet1 | DC1-SPINE1 | Ethernet3 |
| L3 Leaf | DC1-LEAF2A | Ethernet2 | DC1-SPINE2 | Ethernet3 |
| L3 Leaf | DC1-LEAF2B | Ethernet1 | DC1-SPINE1 | Ethernet4 |
| L3 Leaf | DC1-LEAF2B | Ethernet2 | DC1-SPINE2 | Ethernet4 |
| L3 Leaf | DC1-LEAF3A | Ethernet1 | DC1-SPINE1 | Ethernet5 |
| L3 Leaf | DC1-LEAF3A | Ethernet2 | DC1-SPINE2 | Ethernet5 |
| L3 Leaf | DC1-LEAF3B | Ethernet1 | DC1-SPINE1 | Ethernet6 |
| L3 Leaf | DC1-LEAF3B | Ethernet2 | DC1-SPINE2 | Ethernet6 |

## Fabric IP Allocation

### Fabric Point-To-Point Links

| P2P Summary | Available Addresses | Assigned addresses | Assigned Address % |
| ----------- | ------------------- | ------------------ | ------------------ |
| 172.16.255.0/24 | 256 | 24 | 9.38 % |

### Point-To-Point Links Node Allocation

| Leaf Node | Leaf Interface | Leaf IP Address | Spine Node | Spine Interface | Spine IP Address |
| --------- | -------------- | --------------- | ---------- | --------------- | ---------------- |
| DC1-LEAF1A | Ethernet1 | 172.16.255.1/31 | DC1-SPINE1 | Ethernet1 | 172.16.255.0/31 |
| DC1-LEAF1A | Ethernet2 | 172.16.255.3/31 | DC1-SPINE2 | Ethernet1 | 172.16.255.2/31 |
| DC1-LEAF1B | Ethernet1 | 172.16.255.5/31 | DC1-SPINE1 | Ethernet2 | 172.16.255.4/31 |
| DC1-LEAF1B | Ethernet2 | 172.16.255.7/31 | DC1-SPINE2 | Ethernet2 | 172.16.255.6/31 |
| DC1-LEAF2A | Ethernet1 | 172.16.255.9/31 | DC1-SPINE1 | Ethernet3 | 172.16.255.8/31 |
| DC1-LEAF2A | Ethernet2 | 172.16.255.11/31 | DC1-SPINE2 | Ethernet3 | 172.16.255.10/31 |
| DC1-LEAF2B | Ethernet1 | 172.16.255.13/31 | DC1-SPINE1 | Ethernet4 | 172.16.255.12/31 |
| DC1-LEAF2B | Ethernet2 | 172.16.255.15/31 | DC1-SPINE2 | Ethernet4 | 172.16.255.14/31 |
| DC1-LEAF3A | Ethernet1 | 172.16.255.17/31 | DC1-SPINE1 | Ethernet5 | 172.16.255.16/31 |
| DC1-LEAF3A | Ethernet2 | 172.16.255.19/31 | DC1-SPINE2 | Ethernet5 | 172.16.255.18/31 |
| DC1-LEAF3B | Ethernet1 | 172.16.255.21/31 | DC1-SPINE1 | Ethernet6 | 172.16.255.20/31 |
| DC1-LEAF3B | Ethernet2 | 172.16.255.23/31 | DC1-SPINE2 | Ethernet6 | 172.16.255.22/31 |

### Overlay Loopback Interfaces (BGP EVPN Peering)

| Overlay Loopback Summary | Available Addresses | Assigned addresses | Assigned Address % |
| ------------------------ | ------------------- | ------------------ | ------------------ |
| 172.17.255.0/24 | 256 | 8 | 3.13 % |

### Loopback0 Interfaces Node Allocation

| Node | Loopback0 |
| ---- | --------- |
| DC1-SPINE1 | 172.17.255.1/32 |
| DC1-SPINE2 | 172.17.255.2/32 |
| DC1-LEAF1A | 172.17.255.3/32 |
| DC1-LEAF1B | 172.17.255.4/32 |
| DC1-LEAF2A | 172.17.255.5/32 |
| DC1-LEAF2B | 172.17.255.6/32 |
| DC1-LEAF3A | 172.17.255.7/32 |
| DC1-LEAF3B | 172.17.255.8/32 |

### VTEP Loopback VXLAN Tunnel Source Interfaces (Leafs Only)

| VTEP Loopback Summary | Available Addresses | Assigned addresses | Assigned Address % |
| --------------------- | ------------------- | ------------------ | ------------------ |
| 172.17.254.0/24 | 256 | 6 | 2.35 % |

### VTEP Loopback Node allocation

| Node | Loopback1 |
| ---- | --------- |
| DC1-LEAF1A | 172.17.254.3/32 |
| DC1-LEAF1B | 172.17.254.3/32 |
| DC1-LEAF2A | 172.17.254.5/32 |
| DC1-LEAF2B | 172.17.254.5/32 |
| DC1-LEAF3A | 172.17.254.7/32 |
| DC1-LEAF3B | 172.17.254.7/32 |
