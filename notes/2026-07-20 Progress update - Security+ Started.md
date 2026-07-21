# CompTIA Security+ (SY0-701)

**Progress:** Modules 1 and 2 complete - General Security Concepts and Threats, Vulnerabilities & Mitigations done. Module 3 (Security Architecture) starts next.

**TryHackMe:** Cyber Security 101 path - continuing from Module 5 (Networking).

## What I covered this week

- **1.1 Fundamental Security Concepts** - CIA triad, AAA framework, non-repudiation, authentication vs authorisation
- **1.2 Zero Trust** - never trust always verify, microsegmentation, identity as the new perimeter
- **1.3 Deception and Disruption** - honeypots, honeynets, honeyfiles, DNS sinkholes
- **1.4 Security Controls** - control categories (technical, managerial, operational, physical) and types (preventive, detective, corrective, deterrent, compensating, directive)
- **1.5 Change Management and Security** - change advisory boards, approval processes, impact on security posture
- **1.6 Cryptography Basics** - symmetric vs asymmetric encryption, key exchange, cypher types
- **1.7 Asymmetric Encryption** - public/private key pairs, RSA, ECC, how asymmetric solves the key distribution problem
- **1.8 Hashing** - one-way functions, MD5, SHA-1, SHA-256, use cases for integrity verification
- **1.9 Digital Certificates** - X.509 structure, certificate fields, chain of trust, certificate pinning
- **1.10 Public Key Infrastructure** - CA hierarchy, root CA, intermediate CA, certificate lifecycle, CRL and OCSP
- **1.11 Data and Keys** - key storage, key escrow, key stretching (PBKDF2, bcrypt)
- **1.12 Crypto Implementations** - TLS handshake, HTTPS, S/MIME, SSH, IPSec, PGP
- **1.13 Blockchain** - distributed ledger, immutability, use cases beyond cryptocurrency
- **1.14 Non-Cryptographic Data Protection** - DLP, data masking, tokenisation, obfuscation
- **2.1 Threat Actors and Motivations** - nation-state, APT, hacktivist, insider threat, script kiddie - motivations and capability levels
- **2.2 Threat Vectors** - attack surface, message-based, image-based, file-based, voice-based, network-based vectors
- **2.3 Social Engineering** - phishing, spear phishing, whaling, vishing, smishing, pretexting, baiting, tailgating
- **2.4 OS Vulnerabilities and Attacks** - privilege escalation, race conditions, buffer overflows, rootkits
- **2.5 Application Vulnerabilities and Attacks** - injection flaws, improper error handling, memory leaks
- **2.6 Web-based Vulnerabilities and Attacks** - OWASP Top 10, SQL injection, XSS, CSRF, directory traversal
- **2.7 Other Vulnerabilities** - zero-day, supply chain, misconfiguration, weak cypher suites, default credentials
- **2.8–2.12 Malicious Activity and Attack Indicators** - IOCs across malware, OS attacks, application attacks, insider threats and social engineering
- **2.13 Application Attack Indicators** - directory traversal, privilege escalation, replay attacks
- **2.14 Physical Attack Indicators** - skimming, RFID cloning, tailgating
- **2.15 Network Attack Indicators** - DDoS, on-path (MITM), replay, MAC flooding, ARP poisoning, DNS poisoning
- **2.16 Cryptographic Attack Indicators** - downgrade attacks, collision attacks, birthday attacks
- **2.17 Password Attack Indicators** - brute force, dictionary, rainbow table, credential stuffing, password spraying
- **2.18–2.20 Network Segmentation, Access Control, Device Hardening** - defence in depth, least privilege, hardening baselines

## Activities/Labs completed (shown in `labs/` where applicable)

- **1.3.1 Testing a Honeypot** - deployed and observed attacker interaction with a decoy system
- **1.6.1 Examining Symmetric Encryption** - observed AES encryption and decryption in action
- **1.7.1 Exploring Asymmetric Encryption** - compared public/private key operations
- **1.8.1 Verifying Integrity with Hashing** - generated and compared hashes to verify file integrity
- **1.8.1 O.MG No Cable** - testing O.MG funcitonality without a cable
- **2.5.1 Performing a Buffer Overflow** - demonstrated how an overflow can overwrite memory and alter execution flow
- **2.6.1 Abusing Unsanitized Input** - demonstrated input validation failure
- **2.6.2 Grabbing Passwords with SQL Injection** - extracted credentials from a vulnerable database using SQL injection
- **2.6.3 Swiping a Token with XSS** - demonstrated cross-site scripting to steal a session token
- **2.10.1 Capturing Credentials through Social Engineering** - observed a phishing credential capture scenario
- **2.13.1 Recognizing Directory Traversal** - navigated outside intended directory using path traversal
- **2.15.1 Crashing a Target with DoS** - demonstrated a denial of service attack against a target system

## Key things to remember

### Cryptography
- **Symmetric encryption** - same key encrypts and decrypts (AES, 3DES); fast but key distribution is a problem
- **Asymmetric encryption** - public key encrypts, private key decrypts (RSA, ECC); solves key distribution but is slower
- **Hashing** - one-way, produces a fixed-length digest; used for integrity not confidentiality; MD5 and SHA-1 are deprecated, use SHA-256+
- **Digital signature** - hashed with sender's private key; recipient verifies with sender's public key - proves authenticity and integrity
- **TLS handshake** - asymmetric encryption used to exchange a symmetric session key; bulk data then encrypted symmetrically
- **Key stretching** - deliberately slows down hashing to make brute force harder (bcrypt, PBKDF2, Argon2)
- **Certificate fields to know** - subject, issuer, validity period, public key, serial number, signature algorithm

### PKI
- **Root CA** - top of the trust hierarchy; kept offline in most enterprise deployments
- **Intermediate CA** - issues end-entity certificates; if compromised, only its certificates need to be revoked
- **CRL (Certificate Revocation List)** - periodic list of revoked certs; can be slow to update
- **OCSP (Online Certificate Status Protocol)** - real-time cert validity check; preferred over CRL

### Security controls
- **Control categories:** technical (firewalls, encryption), managerial (policies, procedures), operational (training, change management), physical (locks, cameras)
- **Control types:** preventive (stops an attack), detective (identifies it happened), corrective (fixes it), deterrent (discourages it), compensating (alternative control), directive (mandates behaviour)

### Threat actors
- **Nation-state** - highest capability, long-term persistence, often APT
- **APT (Advanced Persistent Threat)** - stealthy, long dwell time, targeted
- **Hacktivist** - ideologically motivated, often DDoS or defacement
- **Insider threat** - most dangerous due to existing access; malicious or unintentional
- **Script kiddie** - low skill, uses existing tools; unsophisticated but noisy

### Web attacks
- **SQL injection** - unsanitised input passed to a database query; can extract, modify, or delete data
- **XSS (Cross-Site Scripting)** - malicious script injected into a page viewed by other users; can steal session tokens
- **CSRF (Cross-Site Request Forgery)** - tricks authenticated user into submitting a malicious request
- **Directory traversal** - using ../ sequences to access files outside the intended directory

### Password attacks
- **Brute force** - tries every possible combination; slow but exhaustive
- **Dictionary attack** - tries words from a wordlist; faster than brute force
- **Rainbow table** - precomputed hash-to-plaintext lookup; defeated by salting
- **Credential stuffing** - uses leaked username/password pairs against other services
- **Password spraying** - tries one common password against many accounts to avoid lockout

## Areas that need more practice

- **Crypto Implementations (1.12)** - the longest lesson in the module; TLS handshake steps and IPSec modes (transport vs tunnel) need reinforcing
- **Certificate chain of trust** - root CA → intermediate CA → end-entity flow needs to be instinctive under exam pressure
- **Attack type distinctions** - on-path, replay, and session hijacking are easy to confuse; worth reviewing before the exam
- **Control type vs category** - mixing these up under time pressure is common; worth drilling until automatic
