# CompTIA Network+ (N10-009)

**Progress:** Section 5 (Network Troubleshooting) complete. Network+ course fully done (41.5 hours) ✓

**TryHackMe:** Cyber Security 101 path - modules 1, 2, 3, and 4 complete.

## What I covered

- **5.4 Performance Issues** - bandwidth, latency, jitter, packet loss and how to identify each
- **5.5 Troubleshooting Tools and Protocols** - overview of the core toolkit for diagnosing network problems
- **5.5.1- Command Line Commands** - ipconfig, ping, tracert, netstat, arp, nslookup
- **5.5.2 - NSLOOKUP and DIG** - querying DNS records from the command line
- **5.5.3 - NMAP** - network scanning, host discovery, port scanning
- **5.5.4 - CDP and LLDP** - Layer 2 neighbour discovery protocols
- **5.5.5–5.5.8** - cable testing, toning, spectrum analysis, fibre optic testing
- **5.5.9 - Network Device Commands** - switch and router CLI commands for troubleshooting

## Key things to remember

### Performance concepts
- **Bandwidth** - maximum theoretical throughput on a link; **throughput** - actual measured data transfer rate (always lower than bandwidth)
- **Latency** - delay between sending and receiving data; measured in milliseconds - high latency kills VoIP and real-time applications
- **Jitter** - variation in latency over time - particularly damaging for voice and video traffic
- **Packet loss** - even small percentages (1–2%) cause significant TCP retransmissions and performance degradation

### Core command line tools
- **ipconfig** (Windows) / **ifconfig** or **ip a** (Linux) - view IP address, subnet mask, default gateway, MAC address
- **ipconfig /all** - shows full adapter details including DNS servers and DHCP lease information
- **ipconfig /release** and **/renew** - force release and renewal of a DHCP lease
- **ping** - tests basic connectivity using ICMP echo request/reply; also measures round-trip latency
- **ping -t** (Windows) - continuous ping; useful for monitoring connectivity during changes
- **tracert** (Windows) / **traceroute** (Linux) - traces the path packets take hop by hop to a destination; identifies where latency or failure occurs
- **netstat** - shows active connections, listening ports, and protocol statistics; **netstat -an** shows all connections with port numbers
- **arp -a** - displays the ARP cache, mapping IP addresses to MAC addresses on the local network
- **route print** (Windows) / **ip route** (Linux) - displays the local routing table

### NSLOOKUP and DIG
- **nslookup** - queries DNS to resolve hostnames to IPs and vice versa; can query specific record types (A, MX, CNAME etc.)
- **nslookup [hostname]** - basic forward lookup
- **nslookup -type=MX [domain]** - query a specific record type
- **DIG** (Domain Information Groper) - Linux/Mac DNS query tool, more detailed output than nslookup; preferred by sysadmins for its verbosity
- **dig [hostname]** - basic query; **dig [hostname] MX** - query specific record type
- Both tools are useful for diagnosing DNS resolution failures, incorrect records, and propagation issues

### NMAP
- **NMAP (Network Mapper)** - open source tool for network discovery, host detection, and port scanning
- **nmap [IP]** - basic scan of a single host, shows open ports
- **nmap -sn [subnet]** - ping sweep to discover live hosts on a network (no port scan)
- **nmap -sS [IP]** - SYN scan (stealth scan) - sends SYN packets without completing the handshake; less likely to appear in logs
- **nmap -sV [IP]** - version detection - attempts to identify the service and version running on open ports
- **nmap -O [IP]** - OS detection - attempts to fingerprint the target operating system
- **nmap -p [port] [IP]** - scan a specific port; **-p-** scans all 65535 ports
- **Port states:** open (service listening), closed (no service, port accessible), filtered (firewall blocking - no response)
- Important to know: NMAP is a dual-use tool - used by administrators for asset discovery and by attackers for reconnaissance. Always ensure you have authorisation before scanning a network.

### CDP and LLDP
- **CDP (Cisco Discovery Protocol)** - Cisco proprietary Layer 2 protocol; allows Cisco devices to advertise themselves to directly connected neighbours
- **LLDP (Link Layer Discovery Protocol)** - vendor-neutral IEEE standard equivalent to CDP; works across multi-vendor environments
- Both operate at Layer 2 so they work even if Layer 3 (IP) is misconfigured - useful for mapping physical topology and verifying connections
- **show cdp neighbors** / **show lldp neighbors** - CLI commands to view directly connected devices

### Physical testing tools
- **Cable tester** - verifies continuity and correct wiring on copper cables; identifies opens, shorts, and miswired pairs
- **Toner and probe** - toner injects a signal onto a cable; probe traces it physically through walls/patch panels to identify which cable is which
- **Spectrum analyser** - identifies wireless interference sources and channel utilisation on 2.4GHz and 5GHz bands
- **OTDR (Optical Time Domain Reflectometer)** - tests fibre optic cables; measures reflections to locate faults, breaks, and connector loss

### Network device CLI commands
- **show interfaces** - displays status and statistics for all interfaces including errors and packet counts
- **show ip interface brief** - quick summary of interface status and IP addresses
- **show running-config** - displays the current active configuration on a Cisco device
- **show vlan brief** - lists configured VLANs and which ports belong to each
- **show spanning-tree** - displays STP topology and port roles/states
- **show ip route** - displays the routing table on a router or Layer 3 switch

## Areas that need more practice

- **NMAP flags and their purposes** - the core flags (-sS, -sV, -O, -sn, -p) and what everything does
- **tracert/traceroute output interpretation** - identifying where a failure or latency spike occurs in the hop-by-hop output
- **netstat output** - reading the state column (ESTABLISHED, LISTENING, TIME_WAIT, CLOSE_WAIT) and knowing what each means
- **CDP vs LLDP** - which is Cisco-proprietary vs open standard, and the CLI commands for each

## Network+ course complete ✓

All 5 sections done. Full course summary:

| Section | Topic | Status |
|---|---|---|
| 1 | Networking Concepts | ✓ Complete |
| 2 | Network Implementation | ✓ Complete |
| 3 | Network Operations | ✓ Complete |
| 4 | Network Security | ✓ Complete |
| 5 | Network Troubleshooting | ✓ Complete |
