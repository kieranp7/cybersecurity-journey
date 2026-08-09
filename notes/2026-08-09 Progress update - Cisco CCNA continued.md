# Cisco CCNA (200-301) Continued

**Progress:** Module 3 complete - Switching done. Module 4 (Internet Protocol) starts next week.

**TryHackMe:** Cyber Security 101 path - continuing through Module 7 (Exploitation Basics).

## What I covered this week

- **3.1 Ethernet Basics** - Ethernet standards, CSMA/CD, half vs full duplex, MAC addresses, frame structure
- **3.2 Switching Overview** - how switches learn MAC addresses, MAC address table, frame forwarding methods (store-and-forward, cut-through, fragment-free), collision vs broadcast domains
- **3.3 Spanning Tree Protocol (STP)** - loop prevention, root bridge election, port roles (root, designated, non-designated), port states (blocking, listening, learning, forwarding, disabled), BPDU
- **3.4 Rapid PVST+** - faster convergence than classic STP, port states (discarding, learning, forwarding), edge ports and PortFast
- **3.5 VLANs** - logical network segmentation, access ports, default VLAN, data vs voice VLANs, why VLANs improve security and performance
- **3.6 VLAN Trunking** - 802.1Q tagging, trunk ports carrying multiple VLANs, native VLAN
- **3.7 VLAN Trunking Protocol (VTP)** - VTP modes (server, client, transparent), VTP domain, risks of VTP in production environments
- **3.8 VLAN Routing** - inter-VLAN routing, router-on-a-stick (subinterfaces), Layer 3 switching as an alternative
- **3.9 Switchport Configuration** - port modes, speed and duplex settings, port security basics, sticky MAC addresses
- **3.10 EtherChannel** - bundling multiple physical links into one logical link, LACP vs PAgP, load balancing across links
- **3.11 Review** - end of module consolidation

## Key things to remember

### Switching fundamentals
- **MAC address table** - switch builds this dynamically by reading source MAC addresses from incoming frames; if destination MAC is unknown the frame is flooded out all ports except the one it arrived on
- **Store-and-forward** - receives entire frame before forwarding, checks for errors; most common in modern switches
- **Cut-through** - starts forwarding after reading destination MAC only; faster but no error checking
- **Collision domain** - each switch port is its own collision domain; switches eliminate collisions on full-duplex links
- **Broadcast domain** - all ports on a switch are in the same broadcast domain by default; VLANs create separate broadcast domains

### Spanning Tree Protocol
- **Purpose** - prevents Layer 2 loops which would cause broadcast storms and bring down the network
- **Root bridge election** - switch with the lowest bridge ID wins; bridge ID = priority (default 32768) + MAC address; lower priority wins, ties broken by lowest MAC
- **Port roles:** root port (best path to root bridge), designated port (forwards traffic on a segment), non-designated port (blocked to prevent loops)
- **Port states:** blocking → listening → learning → forwarding - classic STP takes 30–50 seconds to converge
- **Rapid PVST+** - Cisco implementation of RSTP; converges in ~1–2 seconds instead of 30–50; use PortFast on access ports connected to end devices to skip the listening/learning states
- **BPDU Guard** - shuts down a PortFast-enabled port if it receives a BPDU; prevents rogue switches being plugged in

### VLANs
- **Access port** - assigned to one VLAN; carries untagged traffic; connects to end devices
- **Trunk port** - carries traffic for multiple VLANs using 802.1Q tags; connects switches to other switches or routers
- **Native VLAN** - traffic on the native VLAN is sent untagged across a trunk; both ends must agree on native VLAN or frames are misassigned
- **Voice VLAN** - separates VoIP traffic onto its own VLAN for QoS prioritisation; configured alongside a data VLAN on the same access port

### Inter-VLAN routing
- **Router-on-a-stick** - single physical router interface divided into subinterfaces, one per VLAN; each subinterface tagged with 802.1Q and assigned an IP as the default gateway for that VLAN
- **Layer 3 switch** - more efficient than router-on-a-stick for large environments; uses SVIs (Switched Virtual Interfaces) to route between VLANs internally

### VTP
- **Server mode** - can create, modify, delete VLANs; propagates changes to clients
- **Client mode** - receives and applies VLAN updates from server; cannot make local changes
- **Transparent mode** - does not participate in VTP but forwards VTP advertisements; stores VLANs locally
- **Risk** - a rogue switch with a higher revision number can overwrite the VLAN database across the entire domain; many engineers disable VTP in production

### EtherChannel
- **Purpose** - bundles 2–8 parallel links between switches into one logical link; prevents STP from blocking redundant links and increases bandwidth
- **LACP (Link Aggregation Control Protocol)** - open IEEE standard (802.3ad); preferred
- **PAgP (Port Aggregation Protocol)** - Cisco proprietary
- **All ports in an EtherChannel must have matching speed, duplex, and VLAN configuration**
