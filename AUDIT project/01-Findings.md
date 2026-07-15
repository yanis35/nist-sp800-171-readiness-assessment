# Findings Register

## Confidential — NIST SP 800-171 Readiness Assessment

---

### 1. Purpose

This document contains all findings identified during the NIST SP 800-171 readiness assessment. Each finding describes a gap between the current state and the required security control, provides evidence, assesses risk and impact, and recommends remediation.

Findings with **Critical** or **High** priority require immediate management attention and should be addressed before the next formal assessment or CMMC certification.

---

### 2. Finding Priority Definitions

| Priority | Definition | Remediation Timeline |
|----------|------------|:--------------------:|
| **Critical** | Direct and immediate risk to CUI confidentiality, integrity, or availability. Legal or contractual obligation likely violated. | 0-30 days |
| **High** | Significant risk that could lead to CUI compromise or compliance failure. | 30-90 days |
| **Medium** | Moderate risk. Control weakness that increases attack surface or reduces defense depth. | 90-180 days |
| **Low** | Minor gap. Best practice improvement or administrative deficiency. | 180-365 days |

---

### 3. Critical Findings

---

#### FINDING-001: No System Security Plan (SSP) Exists

| Field | Detail |
|-------|--------|
| **Description** | The organization has not developed a System Security Plan (SSP) documenting the CUI system boundary, environment of operation, security requirement implementation, or system interconnections. The SSP is the foundational document for NIST SP 800-171 compliance and is required under DFARS 252.204-7012. Without an SSP, the organization cannot demonstrate how security requirements are implemented or verified. |
| **Evidence** | EVD-CA-01 — SSP requested; none exists. IT Manager confirmed no SSP has been created. |
| **Risk** | Without an SSP, the organization has no authoritative document defining the CUI system boundary, responsible personnel, or control implementation approach. A third-party assessor or CMMC certifier would immediately identify this as a critical gap. |
| **Impact** | Inability to demonstrate compliance to prime contractor or DoD. Potential contract non-compliance. CMMC certification cannot be achieved without an SSP. |
| **Recommendation** | Develop an SSP using NIST SP 800-171 SSP template (NIST SP 800-171A Appendix B) or an approved alternative. The SSP must document: system boundary, environment of operation, security requirement implementation status, responsible personnel, system interconnections, and authorized users. This assessment's outputs (scope, boundary, asset inventory, control assessment) provide the raw material for the SSP. |
| **Priority** | **Critical** |
| **Reference** | NIST SP 800-171 3.12.4 |

---

#### FINDING-002: No Incident Response Plan

| Field | Detail |
|-------|--------|
| **Description** | The organization has no formal Incident Response Plan (IRP). Incident handling is performed ad hoc by the IT Manager without documented procedures for preparation, detection, analysis, containment, eradication, or recovery. The DFARS 252.204-7012 requirement to report cyber incidents to the DoD within 72 hours is not addressed. |
| **Evidence** | EVD-IR-01, EVD-IR-02 — IR Plan requested; none exists. IT Manager confirmed ad hoc approach. EVD-IR-03 — IT Manager was unaware of the 72-hour reporting requirement. |
| **Risk** | In the event of a cyber incident involving CUI, the organization would be unable to respond effectively. Delays in containment could lead to CUI exfiltration. Failure to report to the DoD within 72 hours is a direct violation of contract terms. |
| **Impact** | Contract non-compliance, potential financial penalties, loss of DoD contract, reputational damage. |
| **Recommendation** | Develop and implement an Incident Response Plan that includes: (1) defined roles and responsibilities, (2) incident classification criteria, (3) step-by-step procedures for detection, analysis, containment, eradication, and recovery, (4) DFARS 72-hour reporting procedure with contact information for the DoD, (5) communication templates, (6) evidence preservation requirements. Conduct a tabletop exercise within 90 days of plan completion. |
| **Priority** | **Critical** |
| **Reference** | NIST SP 800-171 3.6.1, 3.6.2 |

---

#### FINDING-003: Multifactor Authentication Not Fully Deployed

| Field | Detail |
|-------|--------|
| **Description** | MFA is enabled for M365 cloud access (Conditional Access policy requires MFA for all cloud apps), but significant gaps exist: (1) VPN remote access does not require MFA, (2) Property Management SaaS uses password-only authentication, (3) MSP remote maintenance connections do not consistently require MFA. This means approximately 40% of access paths to CUI/PII systems lack MFA protection. |
| **Evidence** | EVD-IA-02 — MFA configuration reviewed. VPN MFA not configured. PM SaaS security settings reviewed — no MFA option enabled. EVD-MA-04 — MSP MFA not confirmed. |
| **Risk** | Compromised passwords for VPN, PM SaaS, or MSP accounts could lead to unauthorized access to CUI/PII systems. Phishing attacks targeting any of these access paths have a high success rate without MFA. |
| **Impact** | Unauthorized access to tenant PII database, CUI contract documents, and all organizational systems via compromised credentials. |
| **Recommendation** | (1) Enable MFA on the VPN gateway for all remote access users. (2) Enable MFA in the Property Management SaaS for all accounts. (3) Require MFA for all MSP remote maintenance connections. (4) Verify MFA enforcement through quarterly testing. (5) Document MFA requirements in the Access Control Policy. |
| **Priority** | **Critical** |
| **Reference** | NIST SP 800-171 3.5.3, 3.1.15, 3.7.5 |

---

### 4. High Priority Findings

---

#### FINDING-004: NAS / File Server Lacks Encryption at Rest

| Field | Detail |
|-------|--------|
| **Description** | The NAS file server (SRV-NAS-001) — the primary repository for CUI documents, contracts, and PII — does not have encryption at rest enabled. While the server is physically located in a locked server room, data on disk is stored in plaintext. |
| **Evidence** | EVD-SC-04 — NAS encryption settings reviewed. No volume encryption or file-level encryption configured. |
| **Risk** | Physical theft of the NAS or its drives would expose all CUI and PII data in plaintext. An attacker with physical access to the server room could extract data from the drives without authentication. |
| **Impact** | Massive data breach of CUI and PII. DFARS incident reporting requirement triggered. Reputational and contractual damage. |
| **Recommendation** | Enable NAS volume encryption (e.g., self-encrypting drive support, LUKS, or NAS-embedded encryption feature). Ensure encryption keys are managed securely (backed up, not stored on the NAS itself). Verify encryption using the NAS management console after implementation. |
| **Priority** | **High** |
| **Reference** | NIST SP 800-171 3.13.14 |

---

#### FINDING-005: No Log Review Process

| Field | Detail |
|-------|--------|
| **Description** | Audit logs are generated by the firewall, NAS, and M365, but are not regularly reviewed. The IT Manager confirmed logs are checked "only when there is a problem." There is no scheduled log review process, no log retention standards, and no alerting on logging failures. |
| **Evidence** | EVD-AU-04 — No evidence of log review. IT Manager interview confirmed ad hoc approach. EVD-AU-07 — No logging failure alerts configured. |
| **Risk** | Security incidents may go undetected for extended periods (weeks or months). An attacker with access to systems could operate without detection. Evidence needed for incident response is available but not examined. |
| **Impact** | Delayed incident detection increases damage from breaches. Unable to meet DFARS incident reporting requirements if incident is not detected within 72 hours. |
| **Recommendation** | Implement a log review process: (1) Define log review frequency (daily for critical systems, weekly for all systems). (2) Assign responsibility to IT staff. (3) Create a log review checklist. (4) Configure logging failure alerts. (5) Establish minimum log retention (12 months recommended). (6) Consider implementing a SIEM or log management tool appropriate for a 20-person organization (e.g., Microsoft Sentinel, Graylog). |
| **Priority** | **High** |
| **Reference** | NIST SP 800-171 3.3.3, 3.3.4 |

---

#### FINDING-006: BYOD and Mobile Device Management Not Implemented

| Field | Detail |
|-------|--------|
| **Description** | The organization has no MDM solution. BYOD devices (estimated 10-12 personal smartphones) access corporate email, calendar, and potentially CUI/PII data without device compliance requirements. No Conditional Access policies enforce device encryption, passcode requirements, or remote wipe for personal devices. Company-issued mobile devices (5) are also not managed through MDM. |
| **Evidence** | EVD-AC-07 — No MDM console or configuration. EVD-AC-08 — BYOD policy exists but is not enforced. EVD-SC-08 — Conditional Access MAM policies not configured. |
| **Risk** | A lost or compromised BYOD device with corporate email access could expose PII and potentially CUI. The organization has no ability to remotely wipe corporate data from a lost personal device. No visibility into which devices access corporate data. |
| **Impact** | Data breach from lost or compromised mobile device. Inability to meet CUI protection requirements for mobile access (3.1.19). Regulatory notification obligations triggered. |
| **Recommendation** | (1) Implement Microsoft Intune (included in Business Premium) for MDM/MAM. (2) Enroll company devices in MDM. (3) Deploy MAM policies for BYOD requiring device encryption, passcode, and allowing selective wipe of corporate data. (4) Configure Conditional Access policies to block access from non-compliant devices. (5) Update BYOD policy to reflect technical enforcement. |
| **Priority** | **High** |
| **Reference** | NIST SP 800-171 3.1.18, 3.1.19, 3.13.19 |

---

#### FINDING-007: No Vulnerability Scanning Program

| Field | Detail |
|-------|--------|
| **Description** | The organization does not perform vulnerability scanning on any systems. No scanning tools are deployed. Vulnerability identification relies solely on vendor notifications and Windows Update. Network devices (firewall, NAS) are never scanned. |
| **Evidence** | EVD-RA-03 — No vulnerability scan results. IT Manager confirmed no scanning is performed. |
| **Risk** | Unknown vulnerabilities in systems, applications, and network devices cannot be remediated. Critical vulnerabilities may exist for months or years without detection. |
| **Impact** | Increased likelihood of successful exploitation. Inability to meet DFACS/NIST requirement for periodic vulnerability scanning. |
| **Recommendation** | (1) Deploy a vulnerability scanning tool (e.g., Nessus Professional, Qualys, or integrated scanning via Microsoft Defender for Business). (2) Scan all in-scope systems at least monthly. (3) Establish a vulnerability remediation SLA (Critical: 14 days, High: 30 days, Medium: 90 days). (4) Document scan results and remediation in a POA&M. |
| **Priority** | **High** |
| **Reference** | NIST SP 800-171 3.11.2, 3.11.3 |

---

#### FINDING-008: No Data Classification or CUI Marking Procedures

| Field | Detail |
|-------|--------|
| **Description** | The organization has no data classification policy or procedure. Employees cannot distinguish CUI from non-CUI data. Documents received from the DoD contract are not marked as CUI. Employees handle all data uniformly without awareness of which data requires enhanced protection. |
| **Evidence** | EVD-AC-01 — Access Control Policy does not address data classification. EVD-AT-03 — No role-based training on CUI handling. CUI Determination (Phase 8) confirmed no CUI markings on any reviewed documents. |
| **Risk** | CUI may be handled, stored, or transmitted without appropriate safeguards. Employees may unintentionally expose CUI through email, file sharing, or removable media. |
| **Impact** | Unauthorized disclosure of CUI. Non-compliance with NIST SP 800-171 CUI protection requirements. |
| **Recommendation** | (1) Develop a data classification policy defining CUI, PII, and internal data categories. (2) Train employees on CUI identification and handling. (3) Implement CUI markings on all CUI documents and emails (CUI banner, dissemination controls). (4) Request CUI designation clarification from the prime contractor. (5) Consider implementing Microsoft 365 sensitivity labels for automatic CUI classification. |
| **Priority** | **High** |
| **Reference** | NIST SP 800-171 3.1.3, 3.2.2 |

---

#### FINDING-009: No Change Management Process

| Field | Detail |
|-------|--------|
| **Description** | System changes are made without formal change management. IT Manager makes configuration changes, applies patches, and installs software without documentation, prior approval, or security impact analysis. MSP changes are not communicated in advance. |
| **Evidence** | EVD-CM-05 — Change management policy does not exist. EVD-CM-06 — No change records available. IT Manager interview confirmed informal process. |
| **Risk** | Unauthorized or improperly tested changes could introduce security vulnerabilities, cause system instability, or disrupt business operations. No audit trail exists to determine what changed during an incident. |
| **Impact** | Increased operational risk. Inability to investigate incidents caused by unauthorized changes. |
| **Recommendation** | (1) Develop a change management policy appropriate for a 20-person organization (tiered — minor/normal/emergency changes). (2) Implement a simple change request form (description, justification, risk assessment, approver). (3) Require security impact analysis for significant changes. (4) Require MSP to submit change requests in advance. (5) Maintain a change log. |
| **Priority** | **High** |
| **Reference** | NIST SP 800-171 3.4.3, 3.4.4 |

---

#### FINDING-010: No POA&M or Continuous Monitoring

| Field | Detail |
|-------|--------|
| **Description** | The organization does not maintain a Plan of Actions and Milestones (POA&M) to track security deficiencies and remediation. No continuous monitoring program exists to verify ongoing effectiveness of security controls. |
| **Evidence** | EVD-CA-02 — POA&M does not exist. EVD-CA-03 — No continuous monitoring program. |
| **Risk** | Identified deficiencies are not tracked to remediation. Security controls may degrade over time without detection. Recurring assessments will find the same gaps. |
| **Impact** | Inability to demonstrate continuous improvement. CMMC certification requires a POA&M. DFARS compliance requires ongoing assessment. |
| **Recommendation** | (1) Create a POA&M using the findings from this assessment. (2) Assign owners and target dates for each finding. (3) Review POA&M monthly. (4) Implement a continuous monitoring approach: define which controls are monitored, how, and how often. (5) Schedule a follow-up assessment in 12 months. |
| **Priority** | **High** |
| **Reference** | NIST SP 800-171 3.12.2, 3.12.3 |

---

### 5. Medium Priority Findings

---

#### FINDING-011: IT Staff Use Single Privileged Account for All Activities

| Field | Detail |
|-------|--------|
| **Description** | IT staff do not maintain separate admin and user accounts. The IT Manager uses a single account with administrative privileges for all activities including email, web browsing, and document editing. This violates the principle of least privilege and increases the risk of credential theft via phishing or web-based attacks. |
| **Evidence** | EVD-AC-13 — Account audit showed single account for IT staff. |
| **Risk** | If the IT Manager's account is compromised (via phishing or malicious website), the attacker gains full administrative access to all systems. Browser-based attacks are the most common vector for credential theft. |
| **Impact** | Full compromise of all organizational systems from a single credential theft. |
| **Recommendation** | (1) Create separate privileged admin accounts for IT staff. (2) Standard user accounts should have no administrative privileges. (3) Admin accounts should be used only for administrative tasks. (4) Enforce MFA on admin accounts. (5) Consider implementing Privileged Identity Management (PIM) in Azure AD for just-in-time admin access. |
| **Priority** | **Medium** |
| **Reference** | NIST SP 800-171 3.1.5, 3.1.6 |

---

#### FINDING-012: VPN Configured for Split-Tunneling

| Field | Detail |
|-------|--------|
| **Description** | The VPN is configured to allow split-tunneling — remote user traffic to the internet does not route through the organizational firewall. This means that when a field employee is connected to VPN, their web traffic bypasses the org's security controls. |
| **Evidence** | EVD-SC-10 — VPN configuration reviewed. Split-tunneling enabled. |
| **Risk** | Remote users' internet traffic bypasses the org firewall, web filtering, and threat detection. Malicious content from the internet can directly reach a device that is simultaneously connected to the corporate network, potentially allowing lateral movement. |
| **Impact** | Increased risk of malware infection on VPN-connected devices. Reduced visibility into remote user activity. |
| **Recommendation** | (1) Reconfigure VPN to full-tunnel mode (all traffic routes through org firewall). (2) Test for performance impact on remote users. (3) If performance is a concern, consider selective tunneling with monitoring rather than full split-tunnel. |
| **Priority** | **Medium** |
| **Reference** | NIST SP 800-171 3.13.7 |

---

#### FINDING-013: No Configuration Baselines or Hardening Standards

| Field | Detail |
|-------|--------|
| **Description** | System configurations are applied based on IT Manager experience rather than documented standards. No CIS benchmarks, STIGs, or organizational hardening standards are used. No baseline configuration documentation exists. |
| **Evidence** | EVD-CM-01 — No baseline documentation. EVD-CM-03 — No hardening standards. |
| **Risk** | Systems may be configured inconsistently, leading to security gaps. New systems deployed without hardened baselines may have insecure defaults. |
| **Impact** | Increased attack surface. Inconsistent security posture across systems. |
| **Recommendation** | (1) Select a hardening standard (CIS Benchmarks recommended for small organizations — free download). (2) Apply to all in-scope systems. (3) Document baseline configurations for each system type. (4) Use GPO to enforce settings where possible. (5) Verify baselines annually. |
| **Priority** | **Medium** |
| **Reference** | NIST SP 800-171 3.4.1, 3.4.2 |

---

#### FINDING-014: No Logon Banner

| Field | Detail |
|-------|--------|
| **Description** | No warning banner is displayed before users log on to workstations or the NAS. Users are not informed that the system is for authorized use only and that activity is monitored. |
| **Evidence** | EVD-AC-11 — Interactive logon message not configured. |
| **Risk** | Reduced legal protection if unauthorized use is prosecuted. Users may not be on notice that their activity is monitored. |
| **Impact** | Legal — diminished ability to hold unauthorized users accountable. |
| **Recommendation** | (1) Configure interactive logon message via GPO with approved text. (2) Ensure message includes: notice of authorized use, monitoring notice, prohibition of unauthorized access, and consent to monitoring. (3) Apply to all in-scope workstations and NAS. |
| **Priority** | **Medium** |
| **Reference** | NIST SP 800-171 3.1.9 |

---

#### FINDING-015: Media Sanitization and Disposal Not Addressed

| Field | Detail |
|-------|--------|
| **Description** | No media sanitization procedure exists. Decommissioned hard drives are stored in a supply closet without sanitization. No documented process for secure disposal of media containing CUI/PII. |
| **Evidence** | EVD-MP-04 — No sanitization procedure. Physical observation confirmed old drives stored in unlocked cabinet. |
| **Risk** | Decommissioned drives containing CUI/PII could be lost, stolen, or improperly discarded, leading to data exposure. |
| **Impact** | Data breach from improperly disposed media. Regulatory penalties. |
| **Recommendation** | (1) Develop a media sanitization policy aligned with NIST SP 800-88. (2) Sanitize or destroy all decommissioned media. (3) Document sanitization/destruction with certificates. (4) Secure media awaiting sanitization in a locked container. |
| **Priority** | **Medium** |
| **Reference** | NIST SP 800-171 3.8.5 |

---

#### FINDING-016: Insider Threat Training Not Provided

| Field | Detail |
|-------|--------|
| **Description** | Security awareness training does not include insider threat awareness. Employees are not trained to recognize indicators of insider threat (unusual access patterns, policy violations, social engineering indicators). |
| **Evidence** | EVD-AT-04 — No insider threat training materials. |
| **Risk** | Insider threats (malicious or negligent) may go undetected. Small organizations with 20 employees are particularly vulnerable to insider risk due to limited segregation of duties. |
| **Impact** | Undetected insider activity could lead to CUI exfiltration or data breach. |
| **Recommendation** | (1) Incorporate insider threat awareness into annual security training. (2) Include common indicators (unusual logon times, large data transfers, policy violations). (3) Define reporting channels. (4) Consider implementing user behavior analytics (available in some security platforms). |
| **Priority** | **Medium** |
| **Reference** | NIST SP 800-171 3.2.3 |

---

#### FINDING-017: No Role-Based Security Training

| Field | Detail |
|-------|--------|
| **Description** | Personnel handling CUI and PII (property managers, construction managers, admin staff) have not received role-specific training on data protection requirements. They handle tenant PII and potential CUI without understanding their security responsibilities. |
| **Evidence** | EVD-AT-03 — No role-based training materials. Property Manager interview confirmed no CUI-specific training. |
| **Risk** | Personnel handling sensitive data may not understand how to protect it. Increased risk of accidental exposure. |
| **Impact** | Accidental CUI/PII disclosure through improper handling. |
| **Recommendation** | (1) Develop role-based training for: CUI handlers (property managers, admin, construction), IT staff (security administration), and all employees (baseline). (2) Document completion. (3) Provide refresher training annually. |
| **Priority** | **Medium** |
| **Reference** | NIST SP 800-171 3.2.2 |

---

### 6. Low Priority Findings

---

#### FINDING-018: Security Awareness Training Completion Not Enforced

| Field | Detail |
|-------|--------|
| **Description** | Annual security awareness training completion rate is approximately 70%. No enforcement mechanism ensures all employees complete training. |
| **Evidence** | EVD-AT-02 — Training records show 70% completion. |
| **Risk** | 30% of employees (6 people) may not be aware of security policies and risks. |
| **Impact** | Reduced overall security awareness across the organization. |
| **Recommendation** | (1) Track training completion and report to Executive monthly. (2) Implement consequences for non-completion (access suspension until training is completed). (3) Use a learning management system or M365 Learning to automate tracking. |
| **Priority** | **Low** |
| **Reference** | NIST SP 800-171 3.2.1 |

---

#### FINDING-019: Inactive Accounts Not Regularly Audited

| Field | Detail |
|-------|--------|
| **Description** | Several inactive accounts were identified (former employees). No automated process detects or disables inactive accounts. |
| **Evidence** | EVD-IA-04 — User account audit revealed inactive accounts. |
| **Risk** | Inactive accounts could be used by attackers for unauthorized access. Orphaned accounts complicate access reviews. |
| **Impact** | Increased attack surface from unused accounts. |
| **Recommendation** | (1) Disable identified inactive accounts immediately. (2) Implement recurring account review (quarterly). (3) Configure Azure AD to detect and report inactive accounts. (4) Set account expiry for temporary/contractor accounts. |
| **Priority** | **Low** |
| **Reference** | NIST SP 800-171 3.5.6 |

---

#### FINDING-020: No Physical Security Policy for Remote Workers

| Field | Detail |
|-------|--------|
| **Description** | Remote workers have no documented physical security requirements for home office environments. Laptops containing CUI may be used in uncontrolled environments without guidance on safeguarding. |
| **Evidence** | EVD-PE-05 — Remote work policy does not include physical security. |
| **Risk** | CUI on remote laptops could be accessed by unauthorized individuals in home office environments (family members, visitors). |
| **Impact** | CUI exposure through inadequate physical safeguards at alternate work sites. |
| **Recommendation** | (1) Update remote work policy to include physical security requirements (locked doors when unattended, privacy screens, device storage when not in use). (2) Include in annual training. |
| **Priority** | **Low** |
| **Reference** | NIST SP 800-171 3.10.6 |

---

### 7. Findings Summary

| ID | Title | Priority | Reference | Status |
|:--:|-------|:--------:|:---------:|:-----:|
| FINDING-001 | No System Security Plan | **Critical** | 3.12.4 | Open |
| FINDING-002 | No Incident Response Plan | **Critical** | 3.6.1, 3.6.2 | Open |
| FINDING-003 | MFA Not Fully Deployed | **Critical** | 3.5.3, 3.1.15, 3.7.5 | Open |
| FINDING-004 | NAS Encryption at Rest | High | 3.13.14 | Open |
| FINDING-005 | No Log Review Process | High | 3.3.3, 3.3.4 | Open |
| FINDING-006 | BYOD / MDM Not Implemented | High | 3.1.18, 3.1.19, 3.13.19 | Open |
| FINDING-007 | No Vulnerability Scanning | High | 3.11.2, 3.11.3 | Open |
| FINDING-008 | No Data Classification / CUI Marking | High | 3.1.3, 3.2.2 | Open |
| FINDING-009 | No Change Management | High | 3.4.3, 3.4.4 | Open |
| FINDING-010 | No POA&M or Continuous Monitoring | High | 3.12.2, 3.12.3 | Open |
| FINDING-011 | IT Single Privileged Account | Medium | 3.1.5, 3.1.6 | Open |
| FINDING-012 | VPN Split-Tunneling | Medium | 3.13.7 | Open |
| FINDING-013 | No Configuration Baselines | Medium | 3.4.1, 3.4.2 | Open |
| FINDING-014 | No Logon Banner | Medium | 3.1.9 | Open |
| FINDING-015 | Media Sanitization Missing | Medium | 3.8.5 | Open |
| FINDING-016 | No Insider Threat Training | Medium | 3.2.3 | Open |
| FINDING-017 | No Role-Based Training | Medium | 3.2.2 | Open |
| FINDING-018 | Training Completion Not Enforced | Low | 3.2.1 | Open |
| FINDING-019 | Inactive Accounts Not Audited | Low | 3.5.6 | Open |
| FINDING-020 | No Remote Work Physical Security | Low | 3.10.6 | Open |

---

### 8. Findings Distribution by Priority

```
Priority Distribution
─────────────────────────────────────────────────
Critical:  ████████████████▋  3 (15%)
High:      █████████████████████████████████████ 7 (35%)
Medium:    █████████████████████████████████████ 7 (35%)
Low:       ██████████▋  3 (15%)
─────────────────────────────────────────────────
Total: 20 findings
```

---

### 9. Findings by NIST SP 800-171 Family

| Family | Findings |
|--------|:--------:|
| AC — Access Control | 3 |
| AT — Awareness & Training | 3 |
| AU — Audit & Accountability | 1 |
| CM — Configuration Management | 2 |
| IA — Identification & Authentication | 1 |
| IR — Incident Response | 1 |
| MA — Maintenance | 0 |
| MP — Media Protection | 1 |
| PS — Personnel Security | 0 |
| PE — Physical Protection | 1 |
| RA — Risk Assessment | 1 |
| CA — Security Assessment | 2 |
| SC — System & Communications Protection | 3 |
| SI — System & Information Integrity | 0 |
| **Cross-Family** | **3** |

---

*Document Version: 1.0*
*Date: July 20, 2026*
