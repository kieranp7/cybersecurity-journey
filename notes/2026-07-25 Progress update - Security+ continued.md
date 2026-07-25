# CompTIA Security+ (SY0-701) Continued

**Progress:** Modules 3 and 4 complete - Security Architecture and Security Operations done. Only module 5 (Security Program Management and Oversight) left.

**TryHackMe:** Cyber Security 101 path - completed up to and including module 6.

## What I covered 

- **3.1 Network Segmentation** - DMZ, screened subnets, VLANs, air gaps, extranet vs intranet
- **3.2 High Availability** - load balancing, clustering, failover, active-active vs active-passive
- **3.3 Virtualisation** - hypervisor types (Type 1 and Type 2), VM escape, containerisation, isolation
- **3.4 Cloud** - cloud service models, shared responsibility model, cloud security considerations
- **3.5 Serverless Computing** - FaaS, event-driven architecture, security implications
- **3.6 IoT** - attack surface, weak defaults, firmware vulnerabilities, network segmentation as mitigation
- **3.7 ICS/SCADA** - operational technology, air-gapped networks, Purdue model, legacy system risks
- **3.8 RTOS and Embedded Systems** - real-time constraints, limited patching, attack surface
- **3.9 Reducing the Attack Surface** - disabling unnecessary services, ports, and protocols
- **3.10 Firewalls** - stateful vs stateless, WAF, NGFW, packet filtering, application layer inspection
- **3.11 IDS/IPS** - signature-based vs anomaly-based, inline vs passive, true/false positive/negative
- **3.12 Secure Communications and Access** - VPN types (site-to-site, remote access), tunnelling protocols, TLS, SSH, jump servers, bastion hosts
- **3.13 Port Security** - MAC address filtering, 802.1X, sticky MAC
- **3.14 SD-WAN and SASE** - software-defined WAN, Secure Access Service Edge, cloud-native security
- **3.15–3.17 Data Classifications and Considerations** - public, private, sensitive, critical; data sovereignty, retention, and disposal
- **3.18–3.20 Redundancy, Alternate Sites, Multiple Platforms** - RAID levels, hot/warm/cold sites, geographic redundancy
- **3.21 Business Continuity** - BCP vs DRP, BIA, MTD, RTO, RPO
- **4.1 Secure Baselines** - hardening standards, CIS benchmarks, configuration management
- **4.2 Attack Surface Reduction** - unnecessary software removal, default credential changes, patch management
- **4.3 Wireless Installation** - site surveys, antenna placement, channel selection
- **4.4 Wireless Security Settings** - WPA2 vs WPA3, EAP types, RADIUS integration, enterprise vs personal mode
- **4.5 Mobile Solutions** - MDM, MAM, BYOD vs COPE vs CYOD, remote wipe
- **4.6 Application Security Management** - SAST, DAST, code signing, sandboxing
- **4.7 Asset Management** - inventory, asset tagging, hardware and software asset lifecycle
- **4.8 Vulnerability Management** - CVE, CVSS scoring, vulnerability scanning vs penetration testing, remediation prioritisation
- **4.9 Monitoring Activities** - log collection, continuous monitoring, alerting thresholds
- **4.10 Monitoring Tools** - SIEM, log aggregation, NetFlow, packet capture, EDR
- **4.11 Firewall Configuration** - rule ordering, implicit deny, inbound vs outbound rules, NAT rules, zone-based firewalls
- **4.12 Intrusion Detection Configuration** - rule tuning, alert thresholds, reducing false positives
- **4.13 Web Traffic Filtering** - URL filtering, content inspection, proxy integration
- **4.14 Operating System Policy** - Group Policy, configuration baselines, enforcing security settings
- **4.15 Network Service Security** - securing DNS, DHCP, NTP - common attack vectors and mitigations
- **4.16 Data Loss Prevention** - DLP policies, endpoint DLP, network DLP, file integrity monitoring
- **4.17 Network Access Control** - NAC frameworks, posture assessment, quarantine VLANs
- **4.18 Identity Management** - IAM, SSO, federation, SAML, OAuth, OIDC, directory services
- **4.19 Access Management** - RBAC, ABAC, MAC, DAC - models and when each is appropriate
- **4.20 Security Automation** - SOAR, playbooks, automated response, scripting for security tasks
- **4.21 Incident Response** - IR lifecycle (preparation, identification, containment, eradication, recovery, lessons learned), IR team roles
- **4.22 Digital Forensics** - order of volatility, chain of custody, forensic imaging, legal hold, e-discovery

## Activities/Labs completed (shown in labs/ where applicable)

- **3.3.1 Deploying Docker Containers** - deployed containerised applications and observed isolation between containers
- **4.14.1 Examining Windows Group Policy** - navigated Group Policy settings and observed how policies enforce security configurations
- **4.16.1 Checking File Integrity** - used hashing to verify whether files had been modified
- **4.19.1 Implementing Access Control** - applied RBAC policies and tested access permissions against different user roles

## Key things to remember

### Network segmentation and architecture
- **DMZ** - semi-trusted zone between the internet and internal network; hosts public-facing services (web servers, mail servers)
- **Air gap** - physical isolation from other networks; used in ICS/SCADA and classified environments
- **Zero trust** ties directly into segmentation - microsegmentation enforces least privilege at the network level
- **Screened subnet** - modern term for DMZ in the Security+ SY0-701 exam; same concept, updated terminology

### Virtualisation and cloud
- **Type 1 hypervisor** - runs directly on hardware (VMware ESXi, Hyper-V); more secure, used in enterprise
- **Type 2 hypervisor** - runs on top of an OS (VirtualBox, VMware Workstation); more convenient, less secure
- **VM escape** - attacker breaks out of a VM to access the hypervisor or other VMs; critical vulnerability
- **Shared responsibility model** - cloud provider secures the infrastructure; customer secures their data, identities, and configurations - scope varies by service model (IaaS/PaaS/SaaS)
- **Containers** - share the host OS kernel, more lightweight than VMs but smaller isolation boundary

### Firewalls and IDS/IPS
- **Stateful firewall** - tracks connection state; knows whether a packet is part of an established session
- **Stateless firewall** - inspects each packet in isolation; faster but less intelligent
- **NGFW (Next-Generation Firewall)** - adds application awareness, user identity, and IPS capabilities
- **WAF (Web Application Firewall)** - inspects HTTP/HTTPS traffic; protects against SQLi, XSS, CSRF
- **IDS** - detects and alerts; passive, does not block
- **IPS** - detects and blocks; inline, can disrupt traffic if misconfigured
- **Signature-based** - matches known attack patterns; low false positives, misses zero-days
- **Anomaly-based** - establishes a baseline and alerts on deviations; catches novel attacks but higher false positives
- **Rule ordering in firewalls** - rules processed top to bottom, first match wins; implicit deny at the bottom catches everything not explicitly permitted

### Identity and access management
- **SAML** - XML-based federation standard; used for SSO between organisations
- **OAuth** - authorisation framework; delegates access without sharing credentials (used by "Login with Google")
- **OIDC (OpenID Connect)** - authentication layer built on top of OAuth
- **RBAC** - permissions assigned to roles, users assigned to roles; easiest to manage at scale
- **ABAC** - permissions based on attributes (user, resource, environment); most flexible, most complex
- **MAC** - labels and clearances; used in government/military environments
- **DAC** - resource owner controls access; most common in standard OS file systems

### Incident response
- **IR phases:** Preparation → Identification → Containment → Eradication → Recovery → Lessons Learned
- **Containment types:** short-term (isolate immediately) vs long-term (patch and harden before returning to production)
- **Order of volatility (forensics):** CPU registers and cache → RAM → swap/pagefile → hard disk → remote logs → archived media - collect most volatile first

### Business continuity
- **RTO** - how quickly must the system be restored?
- **RPO** - how much data loss is acceptable?
- **MTD (Maximum Tolerable Downtime)** - absolute maximum before business impact becomes unacceptable
- **BIA (Business Impact Analysis)** - identifies critical systems and quantifies the impact of their loss

### Vulnerability management
- **CVSS score** - 0–10 scale; 7.0+ is High, 9.0+ is Critical
- **CVE** - standardised identifier for a specific vulnerability
- **Vulnerability scan** - automated, non-exploitative; identifies potential weaknesses
- **Penetration test** - authorised, exploitative; confirms whether a vulnerability is actually exploitable

## Areas that need more practice

- **EAP types for wireless** - EAP-TLS, PEAP, EAP-TTLS differences are easy to confuse; worth a focused review before the exam
- **IAM protocol distinctions** - SAML vs OAuth vs OIDC use cases blur under time pressure; need a clear mental model for each
- **IDS/IPS placement** - knowing when to place inline vs passive, and the implications of each, needs reinforcing
- **CVSS scoring components** - attack vector, attack complexity, privileges required, scope - the individual components need to be solid, not just the overall score
