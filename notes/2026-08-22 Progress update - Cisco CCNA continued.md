# Cisco CCNA (200-301) Continued

**Progress:** Module 4 complete (4.9 Review done). Module 5 (Routing) underway - lessons 5.1 through 5.9 complete.

**TryHackMe:** Cyber Security 101 path - continuing through Module 8 (Web Hacking).

## What I covered this week

- **4.9 Review** - Module 4 consolidation, subnetting and IPv6 recap
- **5.1 Introducing the Route** - what a route is, routing table overview, directly connected routes, static routes, dynamic routes
- **5.2 Routing Basics** - how routers make forwarding decisions, longest prefix match, administrative distance, metric, recursive routing
- **5.3 Packet Delivery on the Same Network** - ARP process, how a host resolves a MAC address before sending, default gateway role
- **5.4 IP Routing Across a Single Router** - how a router processes an incoming packet, routing table lookup, TTL decrement, ARP on the outbound interface
- **5.5 IP Routing Across Multiple Routers** - hop-by-hop packet delivery, how each router makes an independent forwarding decision based on its own routing table
- **5.5.1 Configuring IPv4 Static Routes** - ip route command syntax, next-hop vs exit interface, verifying with show ip route
- **5.5.2 Adding Special Static Routes** - default route (0.0.0.0/0), host routes (/32), summary routes, floating static routes
- **5.6 Routing Protocols Overview** - IGP vs EGP, distance vector vs link-state vs hybrid, RIP, EIGRP, OSPF, BGP overview
- **5.7 Route Selection** - administrative distance values for each routing source, how the router chooses between competing routes
- **5.8 OSPF** - link-state routing, OSPF areas, router types (ABR, ASBR, backbone router), DR/BDR election, LSA types, OSPF metric (cost based on bandwidth), neighbour states
- **5.9 First Hop Redundancy Protocol (FHRP)** - HSRP, VRRP, GLBP, virtual IP and MAC address, active vs standby router

## Key things to remember

### Routing fundamentals
- **Routing table** - router consults this for every packet; contains directly connected networks, static routes, and dynamically learned routes
- **Longest prefix match** - when multiple routes match a destination, the router always uses the most specific one (longest prefix/highest CIDR value)
- **Administrative distance (AD)** - trustworthiness of a routing source; lower is more trusted; used when the same destination is learned from multiple sources
- **Metric** - used to choose the best path when multiple routes to the same destination exist via the same routing protocol; lower is better

### Administrative distance values to memorise
| Route Source | AD |
|---|---|
| Directly connected | 0 |
| Static route | 1 |
| EIGRP summary | 5 |
| eBGP | 20 |
| EIGRP internal | 90 |
| OSPF | 110 |
| RIP | 120 |
| EIGRP external | 170 |
| iBGP | 200 |
| Unknown/unreachable | 255 |

### Static routes
- **Basic syntax:** `ip route [destination network] [subnet mask] [next-hop IP or exit interface]`
- **Default route:** `ip route 0.0.0.0 0.0.0.0 [next-hop]` - matches any destination not in the routing table; the gateway of last resort
- **Host route:** /32 mask, matches one specific IP address
- **Floating static route** - static route with a higher AD than the primary route; sits dormant and only activates if the primary route is lost
- **Verify with:** `show ip route static`

### Routing protocol categories
- **Distance vector** - routers share their routing table with neighbours; slow convergence; RIP uses hop count as metric (max 15 hops)
- **Link-state** - routers share information about their links with all routers in the area; each router builds a complete topology map; faster convergence; OSPF is the main example
- **Hybrid** - combines elements of both; EIGRP is the main example (Cisco proprietary)
- **IGP (Interior Gateway Protocol)** - used within an autonomous system (OSPF, EIGRP, RIP)
- **EGP (Exterior Gateway Protocol)** - used between autonomous systems (BGP - the protocol of the internet)

### OSPF
- **Link-state protocol** - each router floods LSAs (Link State Advertisements) to all routers in the area; every router builds an identical LSDB (Link State Database) and runs SPF algorithm to find best paths
- **Cost metric** - based on bandwidth; cost = reference bandwidth / interface bandwidth; lower cost is preferred; default reference bandwidth is 100Mbps
- **Areas** - OSPF uses areas to limit LSA flooding; Area 0 is the backbone, all other areas must connect to Area 0
- **Router types:**
  - **Backbone router** - has at least one interface in Area 0
  - **ABR (Area Border Router)** - connects two or more areas; summarises routes between areas
  - **ASBR (Autonomous System Boundary Router)** - connects OSPF domain to another routing domain
- **DR/BDR election** - on multi-access networks (Ethernet), routers elect a Designated Router and Backup DR to reduce LSA flooding; highest priority wins (default 1), ties broken by highest router ID
- **Router ID** - 32-bit value used to identify an OSPF router; manually configured or derived from highest loopback IP or highest active interface IP
- **Neighbour states:** Down → Init → 2-Way → Exstart → Exchange → Loading → Full
- **Basic OSPF configuration:**
  - Router(config)# router ospf 1
  - Router(config-router)# router-id 1.1.1.1
  - Router(config-router)# network 192.168.1.0 0.0.0.255 area 0
- **Wildcard mask** - inverse of subnet mask; 0 = must match, 1 = don't care; /24 subnet mask 255.255.255.0 = wildcard 0.0.0.255

### First Hop Redundancy Protocols
- **Problem** - end devices have a single default gateway configured; if that router fails, the host loses connectivity even if another router exists
- **Solution** - FHRP creates a virtual IP and MAC address shared between two or more routers; hosts point to the virtual IP as their gateway
- **HSRP (Hot Standby Router Protocol)** - Cisco proprietary; active and standby router; virtual IP shared; preemption can be configured
- **VRRP (Virtual Router Redundancy Protocol)** - open standard equivalent to HSRP; master and backup routers
- **GLBP (Gateway Load Balancing Protocol)** - Cisco proprietary; adds load balancing across multiple routers unlike HSRP/VRRP which only use one active router at a time
