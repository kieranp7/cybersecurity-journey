# Cisco CCNA (200-301) Continued

**Progress:** Module 4 fully complete - IPv4, binary, subnetting, supernetting, and IPv6 all done.

**TryHackMe:** Cyber Security 101 path - continuing through Module 8 (Web Hacking).

## What I covered this week

- **4.1 IPv4 Basics** - IPv4 address structure, dotted decimal notation, network vs host portions, address exhaustion problem
- **4.2 IP Packet and Interface Types** - IP packet header fields, unicast vs multicast vs broadcast, loopback addresses
- **4.3 Binary Numbering System** - binary to decimal and decimal to binary conversion, powers of 2, relevance to subnet masks
- **4.4 Classful and Classless Addressing** - Class A/B/C address ranges, default subnet masks, limitations of classful addressing, CIDR and classless inter-domain routing
- **4.5 IPv4 Subnetting** - subnet mask mechanics, network address, broadcast address, usable host range, borrowing bits from the host portion
- **4.5.1 Subnetting activity - Moving the Subnet Mask** - worked through subnet calculations, identifying network and host ranges
- **4.6 Subnetting in Other Octets** - subnetting in the second and third octets, block size calculations
- **4.6.1 Subnetting activity** - extended subnetting practice across multiple scenarios
- **4.6.2 Subnetting by Host Requirements** - working backwards from required host count to find the correct subnet mask
- **4.6.3 Grouping Hosts into Subnets** - allocating hosts into appropriately sized subnets for a given network design
- **4.7 Supernetting** - combining multiple contiguous networks into a single summary route, route aggregation, reducing routing table size
- **4.7.1 Supernetting activity** - worked through route aggregation calculations, identifying the correct summary address and prefix length to cover a given set of subnets
- **4.8 IPv6** - 128-bit address structure, hexadecimal notation, address shortening rules (dropping leading zeros, :: for consecutive zero groups), IPv6 address types (global unicast, link-local, loopback, multicast), EUI-64 interface ID generation, why IPv6 was needed

## Key things to remember

### Binary and decimal conversion
- **Powers of 2:** 128, 64, 32, 16, 8, 4, 2, 1 - left to right across an octet
- **Converting decimal to binary:** subtract the largest power of 2 that fits, place a 1, repeat for the remainder
- **Converting binary to decimal:** add up the values where there is a 1
- **255 in binary** = 11111111 · **0 in binary** = 00000000 · **128** = 10000000 · **192** = 11000000

### Classful addressing ranges
- **Class A** - 1.0.0.0 to 126.0.0.0 · default mask /8 · large organisations
- **Class B** - 128.0.0.0 to 191.255.0.0 · default mask /16 · medium organisations
- **Class C** - 192.0.0.0 to 223.255.255.0 · default mask /24 · small organisations
- **127.x.x.x** - reserved for loopback (localhost)
- **169.254.x.x** - APIPA, assigned automatically when DHCP fails

### Private IP ranges (RFC 1918)
- **10.0.0.0/8** - Class A private range
- **172.16.0.0/12** - Class B private range (172.16.0.0 to 172.31.255.255)
- **192.168.0.0/16** - Class C private range

### Subnetting - the core process
- **Subnet mask** - defines which bits are the network portion (1s) and which are the host portion (0s)
- **Block size** = 256 minus the subnet mask value in the relevant octet
- **Network address** - all host bits set to 0 (first address in the subnet, not assignable)
- **Broadcast address** - all host bits set to 1 (last address in the subnet, not assignable)
- **Usable hosts** = 2^n - 2 where n = number of host bits
- **Number of subnets** = 2^s where s = number of borrowed bits

### Subnetting quick reference
| CIDR | Subnet Mask | Hosts per Subnet | Block Size |
|---|---|---|---|
| /24 | 255.255.255.0 | 254 | 256 |
| /25 | 255.255.255.128 | 126 | 128 |
| /26 | 255.255.255.192 | 62 | 64 |
| /27 | 255.255.255.224 | 30 | 32 |
| /28 | 255.255.255.240 | 14 | 16 |
| /29 | 255.255.255.248 | 6 | 8 |
| /30 | 255.255.255.252 | 2 | 4 |

### Subnetting by host requirements
- Identify the number of hosts needed
- Find the smallest power of 2 that is greater than hosts needed + 2 (network and broadcast)
- The number of host bits = log2 of that value
- Subtract host bits from 32 to get the CIDR prefix length

### Supernetting (route aggregation)
- **Purpose** - combines multiple contiguous subnets into a single summary route to reduce routing table size
- The summary route must cover all subnets and nothing more - find the common bits across all network addresses
- Shorter prefix = larger block = more addresses covered
- Used at network boundaries and in OSPF area border routers to reduce LSA flooding

### IPv6
- **Address length** - 128 bits written as 8 groups of 4 hexadecimal digits separated by colons e.g. 2001:0db8:0000:0000:0000:0000:0000:0001
- **Shortening rules** - leading zeros in any group can be dropped · consecutive groups of all zeros can be replaced with :: but only once per address
- **Global unicast** - publicly routable, starts with 2000::/3 (typically 2001: range)
- **Link-local** - automatically assigned to every IPv6 interface, starts with FE80::/10, not routable beyond the local link
- **Loopback** - ::1/128, equivalent to 127.0.0.1 in IPv4
- **Multicast** - starts with FF00::/8, replaces broadcast in IPv6
- **EUI-64** - method of generating a 64-bit interface ID from a 48-bit MAC address by splitting the MAC in half, inserting FFFE in the middle, and flipping the 7th bit
- **No broadcast in IPv6** - replaced entirely by multicast; reduces unnecessary traffic on the network
- **NDP (Neighbor Discovery Protocol)** - replaces ARP in IPv6; uses ICMPv6 messages for address resolution and router discovery
