# Cisco CCNA (200-301) Started

**Progress:** Modules 1 and 2 complete - Network Fundamentals and Network Device Management done.

**TryHackMe:** Cyber Security 101 path - continuing from Module 7 (Exploitation Basics).

## What I covered this week

- **1.1 Intro to Networking** - network types (LAN, WAN, MAN, PAN), network models, basic terminology
- **1.2 OSI Model** - 7-layer review, how each layer maps to real-world protocols and devices
- **1.3 TCP/IP** - 4-layer DoD model, how it maps to OSI, TCP vs UDP, three-way handshake
- **1.4 Network Components** - routers, switches, firewalls, access points, endpoints - roles and functions
- **1.5 Network Topology** - physical vs logical topology, star, mesh, hybrid, spine-leaf
- **1.6 Copper Cable Types** - Cat5e, Cat6, Cat6a, straight-through vs crossover, UTP vs STP
- **1.7 Fibre Optic Cable Types** - single-mode vs multimode, connector types (LC, SC, ST), transceivers
- **1.8 Virtualisation Fundamentals** - hypervisors, virtual switches, how virtualisation affects networking
- **2.1 Connecting to a Cisco Device** - console connections, rollover cable, terminal emulator settings
- **2.2 Basic Cisco Commands** - IOS modes (user EXEC, privileged EXEC, global config, interface config), navigation commands
- **2.3 Configuring for Connectivity** - assigning IP addresses to interfaces, no shutdown command, verifying with show commands
- **2.4 Neighbour Discovery** - CDP and LLDP, show cdp neighbours, show lldp neighbours
- **2.5 Basic Troubleshooting** - ping, traceroute, show interface, show ip interface brief, common failure points

## Key things to remember

### OSI and TCP/IP models
- **OSI layers (bottom to top):** Physical, Data Link, Network, Transport, Session, Presentation, Application
- **TCP/IP layers:** Network Access, Internet, Transport, Application - maps to OSI but collapses Session/Presentation/Application into one
- **Key protocols per layer:** Layer 2 = Ethernet, ARP · Layer 3 = IP, ICMP · Layer 4 = TCP, UDP · Layer 7 = HTTP, DNS, DHCP

### Cisco IOS modes - essential to know
- **User EXEC mode** (`>`) - limited, view-only commands
- **Privileged EXEC mode** (`#`) - full show commands, entered with `enable`
- **Global configuration mode** (`(config)#`) - system-wide changes, entered with `configure terminal`
- **Interface configuration mode** (`(config-if)#`) - interface-specific changes, entered with `interface [type] [number]`
- **Getting back:** `exit` goes up one level · `end` or `Ctrl+Z` returns to privileged EXEC from anywhere

### Essential Cisco show commands
- `show ip interface brief` - quick summary of all interfaces, IP addresses, and status
- `show interfaces` - detailed interface statistics including errors and packet counts
- `show running-config` - current active configuration
- `show version` - IOS version, uptime, hardware info
- `show cdp neighbors` - directly connected Cisco devices
- `show ip route` - routing table

### Configuring an interface
- Interfaces are **shutdown by default** on routers - `no shutdown` is required to bring them up
- Always verify with `show ip interface brief` after configuring

### SSH vs Telnet
- **Telnet** - sends data in plaintext including credentials; legacy, should not be used in production
- **SSH** - encrypted; requires hostname, domain name, RSA key generation, and local user credentials
- SSH configuration requires: `hostname`, `ip domain-name`, `crypto key generate rsa`, `username`, `line vty 0 4` with `transport input ssh`

### CDP and LLDP
- **CDP** - Cisco proprietary, enabled by default on Cisco devices, Layer 2
- **LLDP** - vendor-neutral IEEE standard, disabled by default on Cisco, enabled with `lldp run`
- Both useful for mapping physical topology without needing Layer 3 connectivity

### Copper cables
- **Straight-through** - connects different device types (PC to switch, router to switch)
- **Crossover** - connects same device types (switch to switch, PC to PC) - modern devices use Auto-MDIX so this matters less now
- **Cat5e** - up to 1Gbps
- **Cat6** - up to 10Gbps at shorter distances
- **Cat6a** - up to 10Gbps at 100m

### Fibre optic
- **Single-mode (SMF)** - small core, laser light, long distances (campus to campus, WAN links)
- **Multimode (MMF)** - larger core, LED light, shorter distances (within a building)
- **SFP (Small Form-factor Pluggable)** - transceiver module used to connect fibre to switch/router ports
