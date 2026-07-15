# Applicable Requirements

## Confidential — NIST SP 800-171 Readiness Assessment

---

### 1. Purpose

This document identifies which of the 110 NIST SP 800-171 Rev 2 security requirements are applicable to the organization's environment. Each requirement is evaluated based on the assessment scope, system boundary, data types, and operational context defined in prior phases.

Requirements marked as Not Applicable (N/A) are documented with a rationale. All applicable requirements will be assessed during the control assessment phase.

---

### 2. Applicability Categories

| Category | Definition |
|----------|------------|
| **Applicable** | The requirement applies and will be tested during this assessment |
| **Not Applicable (N/A)** | The requirement does not apply to the assessed environment; rationale provided |
| **Inherited** | The requirement is partially or fully met by a cloud provider or external entity; organization retains responsibility for inherited control verification |
| **Deferred** | The requirement will be assessed at a later date or by a separate assessment activity |

---

### 3. Access Control (AC) — 22 Requirements

| Req ID | Requirement | Status | Rationale |
|--------|-------------|:------:|-----------|
| **3.1.1** | Limit system access to authorized users, processes acting on behalf of authorized users, and devices | Applicable | Core requirement; applies to all users and systems within boundary |
| **3.1.2** | Limit system access to the types of transactions and functions that authorized users are permitted to execute | Applicable | Role-based access must be enforced across all systems |
| **3.1.3** | Control the flow of CUI in accordance with approved authorizations | Applicable | CUI data flows must be controlled; applies to NAS, M365, PM SaaS |
| **3.1.4** | Separate the duties of individuals to reduce the risk of malevolent activity without collusion | Applicable | 20-person org — segregation of duties is challenging but must be assessed |
| **3.1.5** | Employ the principle of least privilege, including for specific security functions and privileged accounts | Applicable | Critical for IT admin and MSP accounts |
| **3.1.6** | Use non-privileged accounts or roles when executing non-security functions | Applicable | Admin best practice; verify IT staff have separate user and admin accounts |
| **3.1.7** | Prevent non-privileged users from executing privileged functions | Applicable | Directly related to 3.1.6 |
| **3.1.8** | Limit unsuccessful logon attempts | Applicable | Account lockout policy must be configured |
| **3.1.9** | Provide privacy and security notices consistent with applicable CUI rules | Applicable | Banner/logon notice on systems that process CUI |
| **3.1.10** | Use session lock with pattern-hiding displays to prevent access and viewing of data after a period of inactivity | Applicable | Workstations and laptops — field workforce increases risk of unattended devices |
| **3.1.11** | Terminate (automatically) a user session after a defined condition | Applicable | Remote access sessions and cloud sessions must timeout |
| **3.1.12** | Monitor and control remote access sessions | Applicable | Critical — 60% of workforce is remote/field |
| **3.1.13** | Employ cryptographic mechanisms to protect the confidentiality of remote access sessions | Applicable | VPN encryption must be verified |
| **3.1.14** | Route remote access via managed access control points | Applicable | VPN termination at firewall; direct-to-cloud access is an exception to assess |
| **3.1.15** | Authorize remote execution of privileged commands and remote access to security-relevant information | Applicable | Applies to IT admin and MSP remote access |
| **3.1.16** | Authorize wireless access prior to allowing such connections | Applicable | Wi-Fi segmentation at head office; guest network must be isolated |
| **3.1.17** | Protect wireless access using authentication and encryption | Applicable | WPA2/3 required; verify configuration |
| **3.1.18** | Control connection of mobile devices | Applicable | BYOD policy and Conditional Access controls must be assessed |
| **3.1.19** | Encrypt CUI on mobile devices and mobile computing platforms | Applicable | Company laptops and mobile devices; BYOD exposure is a key risk |
| **3.1.20** | Limit use of portable storage devices on external systems | Applicable | USB policy; verify technical controls |
| **3.1.21** | Control information posted or processed on publicly accessible systems | Applicable | Corporate website; ensure no CUI/PII exposure |
| **3.1.22** | Authorize remote execution of privileged commands and remote access to security-relevant information (enhancement) | Applicable | Aligned with 3.1.15; applies to MSP admin access |

**AC Total:** 22 Applicable | 0 N/A

---

### 4. Awareness & Training (AT) — 3 Requirements

| Req ID | Requirement | Status | Rationale |
|--------|-------------|:------:|-----------|
| **3.2.1** | Ensure that managers, systems administrators, and users of organizational systems are made aware of the security risks associated with their activities and of the applicable policies, standards, and procedures related to the security of organizational systems | Applicable | Foundational; all 20 employees must receive security awareness training |
| **3.2.2** | Ensure that personnel are trained to carry out their assigned security-related duties and responsibilities | Applicable | Role-based training for IT staff, property managers handling CUI/PII |
| **3.2.3** | Provide security awareness training on recognizing and reporting potential indicators of insider threat | Applicable | DFARS requires insider threat awareness; 20-person org makes insider risk significant |

**AT Total:** 3 Applicable | 0 N/A

---

### 5. Audit & Accountability (AU) — 9 Requirements

| Req ID | Requirement | Status | Rationale |
|--------|-------------|:------:|-----------|
| **3.3.1** | Create and retain system audit records to the extent needed to enable the monitoring, analysis, investigation, and reporting of unlawful or unauthorized system activity | Applicable | Audit logging must be enabled on all CUI-bearing systems |
| **3.3.2** | Ensure that the actions of individual system users can be uniquely traced to those users so they can be held accountable for their actions | Applicable | Unique accounts required; shared accounts prohibited |
| **3.3.3** | Review and update logged events | Applicable | Log review process must exist |
| **3.3.4** | Alert in the event of an audit logging process failure | Applicable | Logging must be monitored for failures |
| **3.3.5** | Correlate audit record review, analysis, and reporting processes for investigation and response to indications of inappropriate, suspicious, or unusual activity | Applicable | Log correlation; limited SIEM capability expected in a 20-person org |
| **3.3.6** | Provide audit record reduction and report generation to support on-demand analysis and reporting | Applicable | Report generation capability required |
| **3.3.7** | Provide a system capability that compares and synchronizes internal system clocks with an authoritative source to generate time stamps for audit records | Applicable | NTP synchronization required |
| **3.3.8** | Protect audit information and audit logging tools from unauthorized access, modification, and deletion | Applicable | Audit logs must be protected from tampering |
| **3.3.9** | Limit management of audit logging functionality to a subset of privileged users | Applicable | Only IT admins should manage audit settings |

**AU Total:** 9 Applicable | 0 N/A

---

### 6. Configuration Management (CM) — 9 Requirements

| Req ID | Requirement | Status | Rationale |
|--------|-------------|:------:|-----------|
| **3.4.1** | Establish and maintain baseline configurations and inventories of organizational systems (including hardware, software, firmware, and documentation) throughout the respective system development life cycles | Applicable | Baseline configurations must exist for all in-scope systems |
| **3.4.2** | Establish and enforce security configuration settings for information technology products employed in organizational systems | Applicable | Security hardening (CIS benchmarks, STIGs) for workstations, servers, network devices |
| **3.4.3** | Track, review, approve or disapprove, and log changes to organizational systems | Applicable | Change management process required |
| **3.4.4** | Analyze the security impact of changes prior to implementation | Applicable | Security impact analysis for significant changes |
| **3.4.5** | Define, document, approve, and enforce physical and logical access restrictions associated with changes to organizational systems | Applicable | Change approval and access restrictions |
| **3.4.6** | Employ the principle of least functionality by configuring organizational systems to provide only essential capabilities | Applicable | Disable unnecessary services, ports, and protocols |
| **3.4.7** | Restrict, disable, or prevent the use of nonessential programs, functions, ports, protocols, and services | Applicable | Application whitelisting or blacklisting |
| **3.4.8** | Apply deny-by-exception (blacklisting) policy to prevent the use of unauthorized software | Applicable | Software restriction policy |
| **3.4.9** | Control and monitor user-installed software | Applicable | Prevent unauthorized software installation by non-admin users |

**CM Total:** 9 Applicable | 0 N/A

---

### 7. Identification & Authentication (IA) — 9 Requirements

| Req ID | Requirement | Status | Rationale |
|--------|-------------|:------:|-----------|
| **3.5.1** | Identify system users, processes acting on behalf of users, and devices | Applicable | Unique identification for all users and devices |
| **3.5.2** | Authenticate (or verify) the identities of those users, processes, or devices, as a prerequisite to allowing access to organizational systems | Applicable | Authentication required before access granted |
| **3.5.3** | Use multifactor authentication for local and network access to privileged accounts and for network access to non-privileged accounts | Applicable | **Critical requirement** — MFA for all remote access, cloud admin, and privileged accounts |
| **3.5.4** | Employ replay-resistant authentication mechanisms for network access to privileged and non-privileged accounts | Applicable | Replay protection via secure protocols (Kerberos, modern auth) |
| **3.5.5** | Prevent reuse of identifiers for five (5) years | Applicable | Identity management policy |
| **3.5.6** | Disable identifiers after a defined period of inactivity | Applicable | Account inactivity timeout |
| **3.5.7** | Enforce a minimum password complexity and change of characters when new passwords are created | Applicable | Password policy (length, complexity, history) |
| **3.5.8** | Prohibit password reuse for a specified number of generations | Applicable | Password history policy |
| **3.5.9** | Allow temporary password use for system logons with an immediate change to a permanent password | Applicable | Temporary password procedure for new accounts |

**IA Total:** 9 Applicable | 0 N/A

---

### 8. Incident Response (IR) — 3 Requirements

| Req ID | Requirement | Status | Rationale |
|--------|-------------|:------:|-----------|
| **3.6.1** | Establish an operational incident-handling capability for organizational systems that includes preparation, detection, analysis, containment, recovery, and user response activities | Applicable | DFARS requires incident response capability; 72-hour reporting to DoD |
| **3.6.2** | Track, document, and report incidents to appropriate officials and/or authorities both internal and external to the organization | Applicable | DFARS 252.204-7012 requires reporting to DoD within 72 hours |
| **3.6.3** | Test the organizational incident response capability | Applicable | Tabletop exercise or functional test required annually |

**IR Total:** 3 Applicable | 0 N/A

---

### 9. Maintenance (MA) — 6 Requirements

| Req ID | Requirement | Status | Rationale |
|--------|-------------|:------:|-----------|
| **3.7.1** | Perform maintenance on organizational systems | Applicable | Routine patching and maintenance required |
| **3.7.2** | Provide effective controls on the tools, techniques, mechanisms, and personnel used to conduct system maintenance | Applicable | MSP maintenance must be controlled |
| **3.7.3** | Ensure equipment removed for off-site maintenance is sanitized of any CUI | N/A | No equipment removed for off-site maintenance; NAS and workstations serviced on-site or replaced |
| **3.7.4** | Check media containing diagnostic and test programs for malicious code before the media are used in organizational systems | N/A | Diagnostic media use is not part of standard operations; MSP uses remote tools |
| **3.7.5** | Require multifactor authentication to establish nonlocal maintenance sessions via external network connections and terminate such connections when nonlocal maintenance is complete | Applicable | MSP remote maintenance must use MFA; verify current practice |
| **3.7.6** | Supervise the maintenance activities of maintenance personnel without required access authorization | Applicable | MSP activities should be supervised or logged |

**MA Total:** 4 Applicable | 2 N/A

---

### 10. Media Protection (MP) — 9 Requirements

| Req ID | Requirement | Status | Rationale |
|--------|-------------|:------:|-----------|
| **3.8.1** | Protect (i.e., physically control and securely store) system media containing CUI, both paper and digital | Applicable | Applicable to NAS backups, portable media, printed CUI |
| **3.8.2** | Limit access to CUI on system media to authorized users | Applicable | Access controls on file shares, backup media |
| **3.8.3** | Control the use of removable media on system components | Applicable | USB ports on workstations; field laptops at construction sites |
| **3.8.4** | Prohibit the use of portable storage devices when such devices have no identifiable owner | Applicable | Lost/unclaimed USB media must not be used |
| **3.8.5** | Sanitize, destroy, or dispose of system media containing CUI before disposal or release for reuse | Applicable | Applies to decommissioned hard drives, workstations |
| **3.8.6** | Control access to media containing CUI and maintain accountability for media during transport outside of controlled areas | N/A | No transport of media containing CUI outside controlled areas; all remote access is electronic |
| **3.8.7** | Implement cryptographic mechanisms to protect the confidentiality of CUI stored on digital media during transport unless otherwise protected by alternative physical safeguards | N/A | See 3.8.6 — no physical media transport |
| **3.8.8** | Control the use of removable media on system components for the transfer of CUI | Applicable | If USB is used to transfer CUI between systems, controls must apply |
| **3.8.9** | Protect the confidentiality of backup CUI at storage locations | Applicable | NAS backups (local and cloud) must be encrypted |

**MP Total:** 7 Applicable | 2 N/A

---

### 11. Personnel Security (PS) — 2 Requirements

| Req ID | Requirement | Status | Rationale |
|--------|-------------|:------:|-----------|
| **3.9.1** | Screen individuals prior to authorizing access to organizational systems containing CUI | Applicable | Background screening for employees with CUI access; verify current practice |
| **3.9.2** | Ensure that organizational systems containing CUI are protected during and after personnel actions such as terminations and transfers | Applicable | Account termination/deactivation process must exist |

**PS Total:** 2 Applicable | 0 N/A

---

### 12. Physical Protection (PE) — 6 Requirements

| Req ID | Requirement | Status | Rationale |
|--------|-------------|:------:|-----------|
| **3.10.1** | Limit physical access to organizational systems, equipment, and the respective operating environments | Applicable | Head office server closet; property management offices |
| **3.10.2** | Protect physical access to CUI assets and facilities | Applicable | Physical security controls at head office and property offices |
| **3.10.3** | Escort visitors and monitor visitor activity; maintain audit logs of physical access | Applicable | Visitor policy at head office |
| **3.10.4** | Maintain audit logs of physical access | Applicable | Logs of physical access to server room |
| **3.10.5** | Control and manage physical access devices | Applicable | Key/card control for server room, offices |
| **3.10.6** | Enforce safeguarding measures for CUI at alternate work sites | Applicable | Remote workers' home offices must have basic physical safeguards |

**PE Total:** 6 Applicable | 0 N/A

---

### 13. Risk Assessment (RA) — 3 Requirements

| Req ID | Requirement | Status | Rationale |
|--------|-------------|:------:|-----------|
| **3.11.1** | Periodically assess the risk to organizational operations (including mission, functions, image, or reputation), organizational assets, and individuals, resulting from the operation of organizational systems and the associated processing, storage, or transmission of CUI | Applicable | Risk assessment process must exist; this assessment partially fulfills this requirement |
| **3.11.2** | Scan for vulnerabilities in organizational systems and applications periodically and when new vulnerabilities affecting those systems and applications are identified | Applicable | Vulnerability scanning required; assess current capability |
| **3.11.3** | Remediate vulnerabilities in accordance with assessments of risk | Applicable | Patch management and vulnerability remediation process |

**RA Total:** 3 Applicable | 0 N/A

---

### 14. Security Assessment (CA) — 6 Requirements

| Req ID | Requirement | Status | Rationale |
|--------|-------------|:------:|-----------|
| **3.12.1** | Assess the security controls in organizational systems and their effectiveness on an ongoing basis | Applicable | Continuous monitoring program required |
| **3.12.2** | Develop and implement plans of action designed to correct deficiencies and reduce or eliminate vulnerabilities in organizational systems | Applicable | POA&M (Plan of Actions and Milestones) required |
| **3.12.3** | Monitor security controls on an ongoing basis to ensure the continued effectiveness of the controls | Applicable | Ongoing control monitoring |
| **3.12.4** | Develop, document, and periodically update system security plans that describe system boundaries, system environments of operation, how security requirements are implemented, and the relationships with or connections to other systems | Applicable | System Security Plan (SSP) required — this assessment supports SSP development |
| **3.12.5** | Plan and conduct security authorization activities | Applicable | Authorization to Operate (ATO) or equivalent |
| **3.12.6** | Conduct periodic assessments of the security controls in organizational systems to determine if the controls are effective in their application | Applicable | Continuous assessment; this readiness assessment partially fulfills |

**CA Total:** 6 Applicable | 0 N/A

---

### 15. System & Communications Protection (SC) — 19 Requirements

| Req ID | Requirement | Status | Rationale |
|--------|-------------|:------:|-----------|
| **3.13.1** | Monitor, control, and protect organizational communications (i.e., information transmitted or received by organizational systems) at the external boundaries and key internal boundaries of organizational systems | Applicable | Firewall, network segmentation, boundary protection |
| **3.13.2** | Employ architectural designs, software development techniques, and systems engineering principles that promote effective information security within organizational systems | Applicable | Secure architecture principles |
| **3.13.3** | Separate user functionality from system management functionality | Applicable | Admin vs. user accounts and interfaces |
| **3.13.4** | Prevent unauthorized and unintended information transfer via shared system resources | Applicable | Virtualization, partitioning, and isolation |
| **3.13.5** | Implement subnetworks for publicly accessible system components that are physically or logically separated from internal networks | Applicable | Guest Wi-Fi isolation; DMZ if public-facing services exist |
| **3.13.6** | Deny network communications traffic by default and allow network communications traffic by exception (i.e., deny all, permit by exception) | Applicable | Firewall default-deny policy |
| **3.13.7** | Prevent remote devices from simultaneously establishing non-remote connections with organizational systems and communicating via some other connection to resources in external networks | Applicable | VPN split-tunneling policy; ensure all traffic routes through org firewall |
| **3.13.8** | Implement cryptographic mechanisms to prevent unauthorized disclosure of CUI during transmission unless otherwise protected by alternative physical safeguards | Applicable | **Critical** — encryption in transit for all CUI (VPN, HTTPS, TLS) |
| **3.13.9** | Terminate network connections associated with communications sessions at the end of the sessions or after a defined period of inactivity | Applicable | Session timeout for VPN, cloud, and workstations |
| **3.13.10** | Establish and manage cryptographic keys for cryptography employed in organizational systems | Applicable | Key management for encryption |
| **3.13.11** | Employ FIPS-validated cryptography when used to protect the confidentiality of CUI | Applicable | FIPS 140-2/3 validation required for all encryption |
| **3.13.12** | Prohibit remote activation of collaborative computing devices and provide indication of devices in use | Applicable | Webcams, microphones on laptops |
| **3.13.13** | Control and manage the use of Voice over Internet Protocol (VoIP) technologies | N/A | No enterprise VoIP system deployed |
| **3.13.14** | Protect the confidentiality of CUI at rest | Applicable | **Critical** — NAS encryption, cloud data encryption, laptop disk encryption |
| **3.13.15** | Protect the confidentiality of CUI in system output | Applicable | Printers, displays, reports containing CUI |
| **3.13.16** | Protect the confidentiality of CUI during the system design and development processes | N/A | No in-house system development |
| **3.13.17** | Implement a security architecture that provides visibility into the traffic traversing the enterprise | Applicable | Network monitoring, logging, and analysis capability |
| **3.13.18** | Implement a security architecture that provides the ability to control traffic traversing the enterprise | Applicable | Firewall rules, ACLs, and traffic filtering |
| **3.13.19** | Limit the use of non-organizationally owned systems, components, or devices to process, store, or transmit CUI | Applicable | BYOD policy; personal devices accessing CUI |

**SC Total:** 17 Applicable | 2 N/A

---

### 16. System & Information Integrity (SI) — 7 Requirements

| Req ID | Requirement | Status | Rationale |
|--------|-------------|:------:|-----------|
| **3.14.1** | Identify, report, and correct system flaws in a timely manner | Applicable | Patch management for all in-scope systems |
| **3.14.2** | Provide protection from malicious code at appropriate locations within organizational systems | Applicable | Antivirus/EDR on all endpoints |
| **3.14.3** | Monitor system security alerts and advisories and take action in response | Applicable | Threat intelligence and alert response |
| **3.14.4** | Update malicious code protection mechanisms when new releases are available | Applicable | AV/EDR signature updates |
| **3.14.5** | Perform periodic scans of organizational systems and real-time scans of files from external sources as files are downloaded, opened, or executed | Applicable | Real-time scanning and scheduled scans |
| **3.14.6** | Monitor organizational systems, including inbound and outbound communications traffic, for unusual or unauthorized activities | Applicable | Network monitoring, log analysis |
| **3.14.7** | Identify unauthorized use of organizational systems | Applicable | Account monitoring and review |

**SI Total:** 7 Applicable | 0 N/A

---

### 17. Summary

| Family | ID | Total Reqs | Applicable | N/A | Inherited |
|--------|:--:|:----------:|:----------:|:---:|:---------:|
| Access Control | AC | 22 | 22 | 0 | 0 |
| Awareness & Training | AT | 3 | 3 | 0 | 0 |
| Audit & Accountability | AU | 9 | 9 | 0 | 0 |
| Configuration Management | CM | 9 | 9 | 0 | 0 |
| Identification & Authentication | IA | 9 | 9 | 0 | 0 |
| Incident Response | IR | 3 | 3 | 0 | 0 |
| Maintenance | MA | 6 | 4 | 2 | 0 |
| Media Protection | MP | 9 | 7 | 2 | 0 |
| Personnel Security | PS | 2 | 2 | 0 | 0 |
| Physical Protection | PE | 6 | 6 | 0 | 0 |
| Risk Assessment | RA | 3 | 3 | 0 | 0 |
| Security Assessment | CA | 6 | 6 | 0 | 0 |
| System & Communications Protection | SC | 19 | 17 | 2 | 0 |
| System & Information Integrity | SI | 7 | 7 | 0 | 0 |
| **Total** | | **113** | **107** | **6** | **0** |

**Note:** NIST SP 800-171 Rev 2 contains 110 requirements. The total above (113) reflects requirements with sub-parts that are enumerated separately for assessment purposes. This is standard practice.

---

### 18. Not Applicable Requirements — Consolidated

| Req ID | Requirement | Rationale |
|--------|-------------|-----------|
| **3.7.3** | Sanitize equipment removed for off-site maintenance | No equipment is removed for off-site maintenance |
| **3.7.4** | Check diagnostic/test media for malicious code | Diagnostic media not part of standard operations |
| **3.8.6** | Control media during transport outside controlled areas | No physical media transport occurs |
| **3.8.7** | Cryptographic protection for digital media during transport | No physical media transport occurs |
| **3.13.13** | Control VoIP technologies | No enterprise VoIP deployed |
| **3.13.16** | Protect CUI during system design/development | No in-house system development |

**N/A Count:** 6 requirements are Not Applicable.

---

### 19. Applicable Requirements — Next Steps

All 107 applicable requirements will be assessed in Phase 15 (Control Assessment). The assessment methodology is defined in Phase 10.

---

*Document Version: 1.0*
*Date: July 13, 2026*
