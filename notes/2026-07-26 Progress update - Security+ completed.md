# CompTIA Security+ (SY0-701) Completed

**Progress:** Module 5 complete - Security Program Management and Oversight done. Security+ course fully complete ✓

**TryHackMe:** Cyber Security 101 path - continuing progress.

## What I covered

- **5.1 Elements of Effective Security Governance** - security policies, standards, procedures, guidelines, governance frameworks, roles and responsibilities
- **5.2 Elements of the Risk Management Process** - risk identification, assessment, response strategies, risk register, likelihood vs impact
- **5.3 Third Party Risk Assessment and Management** - vendor risk, supply chain attacks, due diligence, contracts and SLAs, right-to-audit clauses
- **5.4 Effective Security Compliance** - regulatory frameworks (GDPR, HIPAA, PCI-DSS), compliance monitoring, penalties for non-compliance
- **5.5 Audits and Assessments** - internal vs external audits, penetration testing, vulnerability assessments, compliance audits, attestation
- **5.6 Security Awareness Practices** - phishing simulations, security training programmes, insider threat awareness, culture of security

## Key things to remember

### Security governance
- **Policy** - high-level statement of intent and direction; sets the "what" and "why"
- **Standard** - mandatory requirements that support a policy; sets specific measurable criteria
- **Procedure** - step-by-step instructions for carrying out a task; sets the "how"
- **Guideline** - recommended but not mandatory; provides flexibility
- **Governance frameworks to know:** NIST CSF, ISO 27001, CIS Controls, COBIT - understand their purpose and scope rather than memorising them in full

### Risk management
- **Risk = Likelihood × Impact** - the fundamental formula; both factors must be assessed
- **Risk response strategies:**
  - **Avoid** - eliminate the activity that creates the risk
  - **Transfer** - shift the risk to a third party (insurance, outsourcing)
  - **Mitigate** - implement controls to reduce likelihood or impact
  - **Accept** - acknowledge the risk and consciously choose not to act
- **Residual risk** - risk that remains after controls are applied
- **Risk register** - living document tracking identified risks, their scores, owners, and response actions
- **Inherent risk** - risk level before any controls are applied

### Third-party and supply chain risk
- **SolarWinds attack** - attackers compromised the build pipeline of a widely-used IT monitoring tool; malicious code was signed and distributed as a legitimate software update to thousands of organisations, including US government agencies
- **Key lessons:** software supply chain is an attack vector; code signing alone is insufficient; vendor access should follow least privilege; monitor for anomalous behaviour even from trusted software
- **Third-party risk controls:** vendor assessments, contractual security requirements, right-to-audit clauses, limiting vendor access, continuous monitoring
- **Fourth-party risk** - risk introduced by your vendor's vendors; often overlooked

### Compliance frameworks
- **GDPR** - EU regulation covering personal data of EU residents; applies regardless of where the organisation is based; breach notification within 72 hours
- **HIPAA** - US regulation protecting health information; applies to covered entities and business associates
- **PCI-DSS** - payment card industry standard; applies to any organisation handling card data; 12 core requirements
- **Key distinction:** regulations are legally mandated (GDPR, HIPAA); frameworks are voluntary best practice guides (NIST CSF, ISO 27001) - though contracts or regulations may require adherence to frameworks

### Audits and assessments
- **Internal audit** - conducted by the organisation's own team; less independent but more contextual knowledge
- **External audit** - conducted by a third party; more objective, often required for compliance
- **Attestation** - formal declaration that controls are in place and operating effectively
- **Penetration test vs vulnerability assessment** - pen test actively exploits; VA identifies and reports without exploiting

### OSINT and reconnaissance
- **OSINT (Open Source Intelligence)** - gathering information from publicly available sources: WHOIS, DNS records, social media, job postings, LinkedIn, Shodan, Google dorking
- **Passive reconnaissance** - no direct interaction with the target; uses public sources only; leaves no trace
- **Active reconnaissance** - direct interaction with the target (port scanning, service enumeration); faster and more detailed but detectable
- **Key OSINT sources:** WHOIS, DNS lookups, certificate transparency logs, Shodan, LinkedIn, company websites, job postings (reveal technology stack), GitHub (exposed credentials and configs)
- **Active recon tools covered:** NMAP for host and port discovery, service version detection, OS fingerprinting

## Security+ course - full module summary

| Module | Topic | Status |
|---|---|---|
| 1 | General Security Concepts | ✓ Complete |
| 2 | Threats, Vulnerabilities and Mitigations | ✓ Complete |
| 3 | Security Architecture | ✓ Complete |
| 4 | Security Operations | ✓ Complete |
| 5 | Security Program Management and Oversight | ✓ Complete |

## Areas that need more practice

- **Risk response strategy selection** - exam questions often present a scenario and ask which strategy applies; the line between mitigate and accept can be subtle and requires careful reading
- **Compliance framework scope** - knowing which framework applies to which industry or data type is frequently tested; GDPR vs HIPAA vs PCI-DSS scope needs to be solid
- **OSINT tool awareness** - knowing what each tool is used for (Shodan vs WHOIS vs certificate transparency) rather than just the concept of OSINT as a category
- **Governance document hierarchy** - policy vs standard vs procedure vs guideline is a classic exam question; needs to be instinctive
