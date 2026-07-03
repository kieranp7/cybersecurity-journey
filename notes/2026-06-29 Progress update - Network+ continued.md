# CompTIA Network+ (N10-009) Continued

**Progress:** Section 1 & 2 complete. Section 3 started and will hopefully be completed within the next week.

## What I covered this week

- **1.10 Modern Network Environments** - SDN, network virtualisation, cloud networking, software-defined WAN
- **2.1 Implementing Routing Technologies** - static vs dynamic routing, routing protocols, NAT/PAT
- **2.2 Configuring Switching Technologies and Features** - switching fundamentals, STP, VLANs, trunking
- **2.3 Selecting and Configuring Wireless Devices and Technologies** - WAPs, wireless controllers, WLAN configuration
- **2.4 Physical Installations** - rack layout, cable management, patch panels, punching down twisted pair
- **3.1 Organizational Processes and Procedures** - documentation, change management, network diagrams
- **3.2 Network Monitoring Technologies** - SNMP, syslog, NetFlow, SIEM integration basics

## Key things to remember

### Routing
- **Static routes** are manually configured and don't adapt to changes - used for simple or predictable paths
- **Dynamic routing protocols** adapt automatically: RIP (distance vector, max 15 hops), OSPF (link-state, scales better), EIGRP (Cisco proprietary)
- **NAT** translates private IPs to public IPs; **PAT** maps multiple private IPs to a single public IP using different port numbers
- **Default gateway** is the router interface a host sends traffic to when the destination is outside its local subnet

### Switching
- **STP (Spanning Tree Protocol)** prevents switching loops by blocking redundant paths
- **VLANs** logically segment a network at Layer 2 - devices on different VLANs cannot communicate without a router or Layer 3 switch
- **Trunk ports** carry traffic for multiple VLANs between switches using 802.1Q tagging
- **Access ports** connect end devices and carry traffic for a single VLAN only
- **Inter-VLAN routing** requires either a router-on-a-stick configuration or a Layer 3 switch

### Wireless
- **BSS** (single AP) vs **ESS** (multiple APs sharing the same SSID for seamless roaming)
- **Wireless controllers** centralise management of multiple access points - common in enterprise environments
- **Channel overlap** is a key interference issue on 2.4GHz - channels 1, 6, and 11 are the only non-overlapping ones

### Physical and documentation
- **Patch panels** connect structured cabling to network equipment - punchdown tool used to terminate twisted pair
- **Cable management** matters for airflow, troubleshooting access, and preventing accidental disconnections
- **Network documentation** should always be kept current - includes physical and logical diagrams, IP address schemes, and device inventories

### Network monitoring
- **SNMP** - Simple Network Management Protocol. Agents on devices send data to a management station. Know the three versions: SNMPv1/v2 (community strings, not encrypted), SNMPv3 (encrypted and authenticated - preferred)
- **Syslog** collects log messages from network devices centrally - useful for troubleshooting and security monitoring
- **NetFlow** captures metadata about network traffic flows - used for performance analysis and anomaly detection

## Areas that need more practice

- **Inter-VLAN routing configurations** - the difference between router-on-a-stick and Layer 3 switching can blur
- **STP port states and roles** - the sequence and what happens at each stage needs to be solid
- **Routing protocol distinctions** - RIP vs OSPF vs EIGRP at a high level is clear, but the specific metrics each uses (hop count vs cost vs composite) needs reinforcing
- **SNMP versions** - SNMPv3 advantages over v1/v2
