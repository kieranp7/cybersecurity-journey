# CompTIA Network+ (N10-009) 

**Progress:** Sections 3 and 4 are complete (Network Operations and Network Security). Section 5 (Network Troubleshooting) is underway - lessons 5.1–5.3 done (around 38 hours completed so far for Network+).

**TryHackMe:** Pre-Security path is fully complete. Now on Cyber Security 101 path - modules 1 and 2 done, module 3 in progress up to Active Directory Basics.

## What I covered this week

- **3.3 Disaster Recovery** - backup strategies, site types, RTO and RPO
- **3.4 IPv4 and IPv6 Network Services** - DHCP relay agents, DNS record types, IPv6 addressing
- **3.5 Network Access and Management** - AAA framework, RADIUS, TACACS+, network access control
- **4.1 Network Security Concepts** - encryption, PKI, authentication methods, zero trust
- **4.2 Network Attacks** - common attack types, DoS/DDoS, phishing, physical attacks
- **4.3 Network Defence** - ACLs, firewalls, honeypots, defence in depth
- **5.1 Troubleshooting Methodology** - systematic approach to diagnosing network issues
- **5.2 Common Cabling and Physical Interface Issues** - cable faults, interface errors, hardware troubleshooting
- **5.3 Network Service Issues** - DNS failures, DHCP problems, routing and connectivity faults

## Key things to remember

### Disaster recovery
- **RTO (Recovery Time Objective)** - maximum acceptable time to restore a system after failure
- **RPO (Recovery Point Objective)** - maximum acceptable amount of data loss measured in time - how old can your most recent backup be?
- **Site types:** hot site (fully operational, immediate failover), warm site (partially configured, hours to bring online), cold site (basic infrastructure only, days to bring online)
- **Backup types:** full (everything), incremental (changes since last backup of any kind), differential (changes since last full backup)

### IPv4/IPv6 services and DNS
- **DHCP relay agent** forwards DHCP requests from one subnet to a DHCP server on a different subnet - needed when the server and clients aren't on the same network segment
- **DNS record types to know:** A (IPv4 address), AAAA (IPv6 address), CNAME (alias), MX (mail server), PTR (reverse lookup), TXT (verification/SPF), NS (name server)
- **IPv6 address shortening rules:** consecutive groups of zeros replaced with ::, leading zeros in a group can be dropped

### AAA and network access
- **AAA = Authentication, Authorisation, Accounting** - who are you, what can you do, what did you do
- **RADIUS** - open standard, encrypts only the password in the authentication packet, commonly used for network access
- **TACACS+** - Cisco proprietary, encrypts the entire payload, separates authentication/authorisation/accounting - preferred for device administration

### Network security concepts
- **Encryption in transit vs at rest** - two different problems requiring different solutions
- **PKI (Public Key Infrastructure)** - framework for managing digital certificates and public/private key pairs
- **Zero trust** - never trust, always verify - no implicit trust based on network location, even inside the perimeter
- **Defence in depth** - multiple overlapping security controls so no single failure exposes the system

### Network attacks
- **DoS vs DDoS** - single source vs distributed (botnet) - DDoS is much harder to mitigate
- **Amplification attacks** - attacker sends small requests spoofed as the victim's IP; servers flood the victim with large responses (DNS amplification, NTP amplification)
- **On-path (MITM) attack** - attacker secretly intercepts and potentially alters traffic between two parties
- **Social engineering** - manipulating people rather than systems - phishing, vishing, pretexting, tailgating
- **Evil twin** - rogue wireless access point mimicking a legitimate one to intercept traffic

### ACLs and network defence
- **ACLs (Access Control Lists)** - filter traffic based on rules; applied on router/switch interfaces in a specific direction (inbound or outbound)
- **Standard ACLs** - filter on source IP only; **extended ACLs** - filter on source/destination IP, protocol, and port
- **Implicit deny** - any traffic not explicitly permitted by an ACL is denied by default - important to remember when writing rules
- **Honeypot** - decoy system designed to attract attackers and observe their behaviour without exposing real assets
- **Honeynet** - a collection of interconnected honeypots to mimic full networks, allows more in-depth threat analysis

### Troubleshooting methodology
- **CompTIA's 7-step process:** Identify the problem → Establish a theory → Test the theory → Establish a plan → Implement the solution → Verify functionality → Document findings
- **OSI troubleshooting approach:** start at Layer 1 (physical) and work up, or start at Layer 7 and work down depending on the symptoms
- **Common cabling faults:** open circuit, short circuit, crossed pairs, split pairs - a cable tester identifies these quickly

## Areas that need more practice

- **DNS record types** - A, AAAA, CNAME, MX are solid but PTR, TXT, NS, SOA records and their specific use cases need reinforcing
- **RADIUS vs TACACS+** - the distinction is clear conceptually but the specific technical differences (what gets encrypted, which port each uses) need to stick
- **OSI and DOD model** - I understand the different layers to a point but need more revision on what each layer is and does
- **Subnetting** - still need more practice in subnetting, especially the bit lengths, number of devices/IPs and bit lengths
- **Network service issues** - links directly to the OSI and DOD models, which troubleshooting methods relate to which layer?

