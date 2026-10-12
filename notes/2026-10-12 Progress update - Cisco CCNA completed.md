# Cisco CCNA (200-301) - Course complete

**Progress:** CCNA course fully complete ✓ - Modules 5 (NAT), 6, 7, 8, and 9 all done.

**Slowed down due to starting a new job and having to focus on this, hence the gap in learning.**

**TryHackMe:** Cyber Security 101 path - temporarily paused due to new job.

## What I covered

- **5.10 Network Address Translation (NAT)** - static NAT, dynamic NAT, PAT (Port Address Translation / NAT overload), inside vs outside local vs global addresses
- **5.11 Review** - Module 5 consolidation, routing summary
- **6.1 Remote Control** - Telnet vs SSH recap, out-of-band vs in-band management, console vs VTY access
- **6.2 File Transfer** - TFTP vs FTP vs SCP for IOS image transfers and config backups, copy command syntax
- **6.3 Monitoring** - SNMP versions and components, syslog severity levels, NTP for time synchronisation
- **6.4 Infrastructure** - DHCP server configuration on a Cisco router, DHCP relay (ip helper-address), DNS in the context of network infrastructure
- **6.5 Quality of Service** - QoS models (best-effort, IntServ, DiffServ), traffic classification and marking, queuing strategies, priority for voice and video traffic
- **7.1 Wi-Fi Principles** - 802.11 standards (a/b/g/n/ac/ax), 2.4GHz vs 5GHz, channel overlap, SSID, BSS vs ESS
- **7.2 Cisco Wireless Architectures** - autonomous vs lightweight APs, split-MAC architecture, CAPWAP tunnel between AP and WLC
- **7.3 WLC Configuration** - wireless LAN controller interface types, WLAN profiles, management access
- **8.1–8.5 Local Device Security** - securing console and VTY lines, enable secret vs enable password, service password-encryption, local user database, privilege levels
- **8.6 Password Recovery** - ROMMON mode, confreg register, breaking into a locked device
- **8.7 Remote Access** - SSH hardening, VTY line configuration, transport input ssh, access-class
- **8.8 Access Control Lists (ACLs)** - standard vs extended ACLs, numbered vs named, inbound vs outbound, implicit deny, wildcard masks, placement rules
- **8.9 DHCP Snooping** - prevents rogue DHCP servers, trusted vs untrusted ports, DHCP snooping binding table
- **8.10 Dynamic ARP Inspection (DAI)** - validates ARP packets against the DHCP snooping binding table, prevents ARP poisoning attacks
- **8.11 Layer 2 Port Security** - limiting MAC addresses per port, sticky MAC, violation modes (protect, restrict, shutdown)
- **8.12 AAA** - Authentication, Authorisation, Accounting framework, RADIUS vs TACACS+ on Cisco devices, 802.1X port-based access control
- **8.13 Wireless Security** - WPA2 vs WPA3, PSK vs Enterprise mode, EAP, RADIUS integration for wireless authentication
- **9.1 Network Automation Overview** - why automation matters, limitations of manual CLI management at scale
- **9.2 Software Defined Networks (SDN)** - control plane vs data plane separation, centralised controller, northbound vs southbound APIs
- **9.3 JSON** - key-value pairs, objects, arrays, how network devices return data in JSON format via APIs
- **9.4 REST APIs** - HTTP methods (GET, POST, PUT, DELETE), status codes, headers, authentication, how to interact with network device APIs
- **9.5 Management Mechanisms** - NETCONF, RESTCONF, gRPC, Ansible, Puppet, Chef - model-driven programmability
- **9.6 AI in Network Operations** - AI/ML use cases in networking (anomaly detection, predictive maintenance, intent-based networking)

## Key things to remember

### NAT and PAT
- **Static NAT** - one-to-one mapping of a private IP to a public IP; used for servers that need a consistent public address
- **Dynamic NAT** - maps private IPs to a pool of public IPs on demand; one-to-one but the public IP is not fixed
- **PAT (NAT overload)** - maps many private IPs to a single public IP using different port numbers; what virtually every home and small office router uses
- **Inside local** - private IP address of the inside host
- **Inside global** - public IP address representing the inside host (as seen from the outside)
- **Outside local** - IP address of the outside host as seen from inside the network
- **Outside global** - actual IP address of the outside host
- **Verify NAT:** `show ip nat translations` · `show ip nat statistics`

### IP services - key commands
- **DHCP on a router:**
  - ip dhcp excluded-address 192.168.1.1 192.168.1.10
  - ip dhcp pool LAN
  - network 192.168.1.0 255.255.255.0
  - default-router 192.168.1.1
  - dns-server 8.8.8.8
- **DHCP relay:** `ip helper-address [DHCP server IP]` applied on the router interface facing the client subnet
- **NTP client:** `ntp server [NTP server IP]` - synchronised time is critical for log correlation and certificate validity
- **Syslog severity levels (0–7):** Emergency, Alert, Critical, Error, Warning, Notice, Informational, Debug - lower number = higher severity

### ACLs
- **Standard ACL** - filters on source IP only; numbered 1–99 and 1300–1999; place as close to the destination as possible
- **Extended ACL** - filters on source IP, destination IP, protocol, and port; numbered 100–199 and 2000–2699; place as close to the source as possible
- **Implicit deny** - every ACL ends with an invisible `deny any` - if no rule matches, traffic is dropped
- **Wildcard mask** - inverse of subnet mask; 0 = must match, 1 = ignore; 0.0.0.255 matches any host in a /24
- **Named ACL syntax:**
  - ip access-list extended BLOCK_HTTP
  - deny tcp any host 10.0.0.1 eq 80
  - permit ip any any
- **Apply to interface:** `ip access-group [ACL name/number] in|out`

### Layer 2 security
- **DHCP Snooping** - designate uplink ports as trusted (`ip dhcp snooping trust`); all other ports are untrusted and will drop DHCP server replies; builds a binding table of IP-to-MAC-to-port mappings
- **Dynamic ARP Inspection** - uses the DHCP snooping binding table to validate ARP packets; drops ARP replies that don't match known bindings; prevents ARP poisoning and MITM attacks
- **Port security violation modes:**
  - **Shutdown** - port goes to err-disabled state; must be manually re-enabled; default and most secure
  - **Restrict** - drops violating frames, logs and increments violation counter, port stays up
  - **Protect** - drops violating frames silently, no logging

### Device hardening essentials
- **Enable secret** - always use `enable secret` not `enable password`; secret uses MD5 hash, password stores in plaintext
- **service password-encryption** - encrypts all plaintext passwords in the config with a weak reversible cipher; better than nothing but not strong
- **Privilege levels** - 0 (no access), 1 (user EXEC), 15 (full privileged EXEC); can define custom levels 2–14
- **Console and VTY hardening:** set exec-timeout, require login local, restrict VTY to SSH only with `transport input ssh`

### SDN and automation
- **Control plane** - makes routing and switching decisions (where to send traffic)
- **Data plane** - actually forwards the traffic based on control plane instructions
- **SDN** - separates these; centralised controller handles the control plane, network devices just forward
- **Northbound API** - between the SDN controller and management applications (REST API)
- **Southbound API** - between the SDN controller and network devices (OpenFlow, NETCONF)
- **NETCONF** - uses XML over SSH to configure network devices; model-driven
- **RESTCONF** - REST-based version of NETCONF; uses HTTP and JSON or XML
- **Ansible** - agentless automation tool; uses SSH and YAML playbooks; popular for network automation

### REST API basics
- **GET** - retrieve data
- **POST** - create new data
- **PUT** - update existing data
- **DELETE** - remove data
- **Common status codes:** 200 OK · 201 Created · 400 Bad Request · 401 Unauthorised · 403 Forbidden · 404 Not Found · 500 Internal Server Error

## CCNA course - full module summary

| Module | Topic | Status |
|---|---|---|
| 1 | Network Fundamentals | ✓ Complete |
| 2 | Network Device Management | ✓ Complete |
| 3 | Switching | ✓ Complete |
| 4 | Internet Protocol (IP) | ✓ Complete |
| 5 | Routing | ✓ Complete |
| 6 | IP Services | ✓ Complete |
| 7 | Wireless | ✓ Complete |
| 8 | Security Fundamentals | ✓ Complete |
| 9 | Automation and Programmability | ✓ Complete |
