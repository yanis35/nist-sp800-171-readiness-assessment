# Control Assessment Matrix

## Confidential — NIST SP 800-171 Readiness Assessment

---

### 1. Purpose

This document contains the complete assessment results for all 107 applicable NIST SP 800-171 Rev 2 security requirements. Each control is rated as **Implemented (I)**, **Partially Implemented (PI)**, **Not Implemented (NI)**, or **Not Applicable (N/A)** with supporting rationale and evidence references.

The 35 controls rated PI or NI represent **findings** that will be carried forward into Phase 16 (Findings) and Phase 17 (Gap Analysis).

---

### 2. Assessment Summary

| Rating | Count | Percentage |
|--------|:-----:|:----------:|
| **Implemented (I)** | 57 | 53% |
| **Partially Implemented (PI)** | 23 | 22% |
| **Not Implemented (NI)** | 12 | 11% |
| **Not Applicable (N/A)** | 6 | 6% |
| **Not Assessed (insufficient evidence)** | 9 | 8% |
| **Total Applicable** | **107** | **100%** |

**Compliance Score: 53%** (57 of 107 applicable controls fully implemented)

---

### 3. Access Control (AC) — 22 Controls

| Req | Description | Rating | Evidence Summary | Rationale |
|:---:|-------------|:------:|------------------|-----------|
| 3.1.1 | Limit access to authorized users | **PI** | EVD-AC-01, EVD-AC-02 | User accounts managed in AD. No shared accounts identified. **Gap:** No periodic access review process documented. Termination offboarding is informal — IT removes access when notified, but no automated trigger. |
| 3.1.2 | Limit access to authorized functions | **PI** | EVD-AC-01, EVD-AC-03 | Basic RBAC exists (AD groups for file share access). PM SaaS has role-based permissions. **Gap:** No formal RBAC matrix document. Construction staff have broader access than strictly necessary due to lack of granular permissions. |
| 3.1.3 | Control flow of CUI | **NI** | EVD-AC-01, EVD-SC-08 | **Gap:** No data classification policy. No DLP controls configured in M365. No CUI marking or handling procedures. Data flows are uncontrolled — employees determine sharing discretionally. |
| 3.1.4 | Separate duties | **PI** | EVD-AC-01 | IT Manager handles both admin and user support functions — this is expected for a 2-person IT team. **Gap:** No documented segregation of duties. Compensating controls (audit logging) exist but are not reviewed. |
| 3.1.5 | Least privilege | **PI** | EVD-AC-03, EVD-AC-13 | Admin accounts limited to IT (2) and MSP (2). **Gap:** Some standard users have local admin rights on their workstations. No periodic privilege review. |
| 3.1.6 | Non-privileged accounts for non-security functions | **NI** | EVD-AC-13 | **Gap:** IT staff do not maintain separate admin and user accounts. IT Manager uses a single account with elevated privileges for all activities including email and browsing. |
| 3.1.7 | Prevent non-privileged from executing privileged functions | **PI** | EVD-AC-13, EVD-CM-04 | UAC is enabled on all workstations. **Gap:** Standard users with local admin rights (identified in 3.1.5) can install software and change system settings. |
| 3.1.8 | Limit unsuccessful logon attempts | **I** | EVD-AC-10 | Account lockout configured: 5 attempts, 15-minute lockout duration. Policy aligns with NIST guidance. |
| 3.1.9 | Provide privacy and security notices | **NI** | EVD-AC-11 | **Gap:** No logon banner configured on workstations or on NAS. Users see no warning about authorized use or CUI protection. |
| 3.1.10 | Session lock with pattern-hiding displays | **I** | EVD-AC-09 | Screen saver timeout set to 10 minutes. Password required on resume. GPO enforced. |
| 3.1.11 | Terminate sessions after defined conditions | **PI** | EVD-AC-09, EVD-SC-11 | Workstation session lock is configured (3.1.10). VPN idle timeout is set to 30 minutes. **Gap:** M365 web app sessions do not have enforced timeout. PM SaaS timeout not confirmed. |
| 3.1.12 | Monitor and control remote access sessions | **PI** | EVD-AC-04, EVD-AC-05 | VPN is primary remote access method. Connection logs are captured. **Gap:** No active monitoring of remote access logs. Direct-to-cloud access bypasses VPN and is not monitored separately. |
| 3.1.13 | Encrypt remote access sessions | **I** | EVD-AC-05, EVD-SC-03 | VPN uses AES-256 encryption. TLS for cloud access. FIPS 140-2 validated. |
| 3.1.14 | Route remote access via managed access control points | **PI** | EVD-AC-05, EVD-SC-02 | VPN routes through firewall for internal system access. **Gap:** Direct-to-cloud access (M365, PM SaaS) does not route through the org VPN. No policy restricting this. |
| 3.1.15 | Authorize remote execution of privileged commands | **PI** | EVD-AC-04, EVD-IA-02, EVD-MA-04 | MSP remote admin requires VPN + MFA. Internal IT admin uses VPN. **Gap:** No formal authorization process documented for remote privileged access. |
| 3.1.16 | Authorize wireless access | **I** | EVD-AC-06 | Wi-Fi requires authentication. Corporate SSID uses WPA2-Enterprise. Guest SSID available for visitors with internet-only access. |
| 3.1.17 | Protect wireless access | **I** | EVD-AC-06 | WPA2-Enterprise with AES. No WEP. Pre-shared key on guest SSID rotated quarterly. |
| 3.1.18 | Control connection of mobile devices | **NI** | EVD-AC-07, EVD-AC-08 | **Gap:** No MDM solution deployed. BYOD policy exists but is not enforced technically. Employees can connect any personal device to corporate email without device compliance checks. Conditional Access policies for mobile devices are not configured. |
| 3.1.19 | Encrypt CUI on mobile devices | **PI** | EVD-AC-07, EVD-SC-04 | Company laptops have BitLocker (verified on sample). **Gap:** BYOD mobile devices access corporate email and potentially CUI without device-level encryption requirements. No MAM policy to enforce encryption on personal devices. |
| 3.1.20 | Limit use of portable storage devices | **PI** | EVD-AC-12 | USB write restriction is configured via GPO. **Gap:** Restriction applies only to company-managed workstations. Field laptops used at construction sites may have USB restrictions disabled for contractor file exchange. |
| 3.1.21 | Control information on publicly accessible systems | **I** | EVD-AC-01 | Corporate website is informational only. No login, no data collection, no content management system connected to internal systems. No evidence of CUI/PII exposure. |
| 3.1.22 | Authorize remote execution of privileged commands (enhanced) | **NI** | EVD-AC-04, EVD-IA-02 | **Gap:** No Just-In-Time (JIT) or Privileged Access Management (PAM) solution. MSP uses standing privileged access. No session recording or detailed audit trail for privileged remote sessions. |

**AC Summary:** 5 I, 10 PI, 6 NI, 0 N/A, 1 Not Assessed

---

### 4. Awareness & Training (AT) — 3 Controls

| Req | Description | Rating | Evidence Summary | Rationale |
|:---:|-------------|:------:|------------------|-----------|
| 3.2.1 | Security awareness training | **PI** | EVD-AT-01, EVD-AT-02 | Annual security awareness training is conducted. Attendance records exist. **Gap:** Training is generic and not tailored to CUI handling or phishing awareness. No testing of comprehension. Records show 70% completion rate — not enforced. |
| 3.2.2 | Role-based training | **NI** | EVD-AT-03 | **Gap:** No role-specific training for personnel handling CUI/PII. Property managers, who handle the most sensitive data, have not received specific training on tenant PII protection or CUI identification. IT staff have no security-specific training. |
| 3.2.3 | Insider threat awareness | **NI** | EVD-AT-04 | **Gap:** No insider threat awareness training exists. Employees are not trained to recognize indicators of insider threat. Reporting channels are not defined. |

**AT Summary:** 0 I, 1 PI, 2 NI, 0 N/A, 0 Not Assessed

---

### 5. Audit & Accountability (AU) — 9 Controls

| Req | Description | Rating | Evidence Summary | Rationale |
|:---:|-------------|:------:|------------------|-----------|
| 3.3.1 | Create and retain audit records | **PI** | EVD-AU-01, EVD-AU-02, EVD-AU-03 | Audit logging enabled on NAS (file access, logon). Firewall logging enabled. M365 audit logging enabled. **Gap:** No centralized log collection. Logs stored locally on each system — a compromise could result in log deletion. Log retention not standardized across systems. |
| 3.3.2 | Uniquely trace user actions | **I** | EVD-AU-02, EVD-IA-04 | All users have unique accounts. No shared accounts identified. AD and M365 logs identify individual user actions. |
| 3.3.3 | Review and update logged events | **NI** | EVD-AU-04 | **Gap:** No log review process exists. Firewall and NAS logs are not regularly reviewed. IT Manager reported logs are checked "only when there is a problem." No evidence of regular log review. |
| 3.3.4 | Alert on audit logging failure | **NI** | EVD-AU-07 | **Gap:** No alerting configured for logging failures. IT Manager would not know if logging stopped on the NAS or firewall until an incident occurred. |
| 3.3.5 | Correlate audit record review | **NI** | EVD-AU-04, EVD-IR-01 | **Gap:** No SIEM or log correlation tool. Logs from different systems are not correlated. Incident investigation would require manual log collection from each system independently. |
| 3.3.6 | Provide audit record reduction and reporting | **PI** | EVD-AU-01, EVD-AU-04 | M365 audit log search provides basic reporting. NAS and firewall logs can be queried. **Gap:** No standardized reporting process. Reports are generated ad hoc if requested. |
| 3.3.7 | Synchronize clocks with authoritative source | **I** | EVD-AU-06 | NTP configured on all network devices and servers. Time source is pool.ntp.org. All systems synchronized. |
| 3.3.8 | Protect audit information from unauthorized access | **PI** | EVD-AU-05 | NAS audit logs are protected by file permissions. M365 audit logs protected by Azure AD. **Gap:** Firewall logs are stored on the firewall itself with admin-only access — adequate but could be tampered with if admin account is compromised. |
| 3.3.9 | Limit audit logging management to privileged users | **I** | EVD-AU-05 | Only IT administrators can modify audit logging settings. Standard users have no access to audit configuration. |

**AU Summary:** 3 I, 2 PI, 4 NI, 0 N/A, 0 Not Assessed

---

### 6. Configuration Management (CM) — 9 Controls

| Req | Description | Rating | Evidence Summary | Rationale |
|:---:|-------------|:------:|------------------|-----------|
| 3.4.1 | Establish baseline configurations | **NI** | EVD-CM-01, EVD-CM-08 | **Gap:** No documented baseline configurations for any system. No formal hardware/software inventory. Asset inventory for this assessment was created from scratch — the organization did not maintain one. |
| 3.4.2 | Establish and enforce security configuration settings | **PI** | EVD-CM-03, EVD-CM-04 | Some security settings configured via GPO (password policy, audit policy). **Gap:** No formal security baseline or hardening standard (CIS, STIG) is used. Configuration is done based on IT Manager's experience — inconsistent across systems. |
| 3.4.3 | Track, review, and log changes | **NI** | EVD-CM-05, EVD-CM-06 | **Gap:** No change management process. Changes are made by IT Manager directly without documentation, approval, or testing. MSP changes are not communicated in advance. |
| 3.4.4 | Analyze security impact of changes | **NI** | EVD-CM-05 | **Gap:** No security impact analysis is performed before changes. Patching, configuration changes, and software installations are applied without assessing security implications. |
| 3.4.5 | Define and enforce access restrictions for changes | **PI** | EVD-CM-05 | Physical access to systems is restricted (server room locked). **Gap:** No formal policy defining who can make changes. In practice, IT Manager and MSP make all changes — but no documented authorization. |
| 3.4.6 | Employ least functionality | **PI** | EVD-CM-03, EVD-CM-04 | Windows systems have default services. **Gap:** No review of unnecessary services, ports, or protocols. No formal least-functionality configuration applied. |
| 3.4.7 | Restrict nonessential programs | **PI** | EVD-CM-07 | Standard users cannot install software (with noted exceptions where local admin rights exist). **Gap:** No application whitelisting or blacklisting. Users can run any software that is installed by IT. |
| 3.4.8 | Apply deny-by-exception policy | **NI** | EVD-CM-07 | **Gap:** No deny-by-exception or allow-by-exception policy. Software execution is deny-by-default only to the extent that standard users cannot install — but once installed, no restrictions on execution. |
| 3.4.9 | Control and monitor user-installed software | **PI** | EVD-CM-07 | GPO restricts standard users from installing software (with noted exceptions). **Gap:** Users with local admin rights can install software unmonitored. No software inventory maintained. |

**CM Summary:** 0 I, 4 PI, 5 NI, 0 N/A, 0 Not Assessed

---

### 7. Identification & Authentication (IA) — 9 Controls

| Req | Description | Rating | Evidence Summary | Rationale |
|:---:|-------------|:------:|------------------|-----------|
| 3.5.1 | Identify users, processes, and devices | **I** | EVD-IA-01, EVD-IA-04, EVD-IA-05 | All users have unique AD accounts. Service accounts are documented. Devices are identified via AD computer objects. |
| 3.5.2 | Authenticate identities prior to access | **I** | EVD-IA-01, EVD-AC-01 | Authentication required for all system access. No anonymous or guest access enabled. |
| 3.5.3 | Use multifactor authentication | **PI** | EVD-IA-02 | **CRITICAL FINDING.** MFA is enabled for M365 cloud access. Conditional Access policy requires MFA for all cloud apps. **Gap:** VPN does not require MFA. PM SaaS uses password-only authentication. MSP remote access does not require MFA for all connections. Approximately 40% of user access paths lack MFA. |
| 3.5.4 | Employ replay-resistant authentication | **PI** | EVD-IA-07 | Kerberos in use for on-prem. Modern authentication enabled for M365. NTLMv2 is enabled (NTLMv1 believed to be disabled but not confirmed). **Gap:** Legacy authentication protocols may still be enabled. Need to verify NTLMv1 status. |
| 3.5.5 | Prevent identifier reuse for 5 years | **I** | EVD-IA-01 | Policy prohibits identifier reuse for 5 years. AD does not allow reuse of deleted account names. |
| 3.5.6 | Disable identifiers after inactivity | **PI** | EVD-IA-01, EVD-IA-04 | AD disable policy exists. **Gap:** Several inactive accounts identified (former employees, terminated contractors) that were not disabled. No automated process for detecting inactive accounts. |
| 3.5.7 | Enforce minimum password complexity and character changes | **I** | EVD-IA-03 | Password policy: 14-character minimum, complexity enabled, maximum age 90 days. Meets NIST guidance. |
| 3.5.8 | Prohibit password reuse | **I** | EVD-IA-03 | Password history: 24 passwords remembered. |
| 3.5.9 | Allow temporary passwords with immediate change | **I** | EVD-IA-06 | New accounts require password change at next logon. Password reset procedure follows same requirement. |

**IA Summary:** 6 I, 3 PI, 0 NI, 0 N/A, 0 Not Assessed

---

### 8. Incident Response (IR) — 3 Controls

| Req | Description | Rating | Evidence Summary | Rationale |
|:---:|-------------|:------:|------------------|-----------|
| 3.6.1 | Establish incident-handling capability | **NI** | EVD-IR-01, EVD-IR-02 | **Gap:** No formal Incident Response Plan exists. Incident response is handled ad hoc by IT Manager. No documented procedures for detection, analysis, containment, eradication, or recovery. No mention of DFARS 72-hour reporting requirement. |
| 3.6.2 | Track, document, and report incidents | **NI** | EVD-IR-03 | **Gap:** No incident tracking system or log. Past incidents are documented in email if at all. No reporting procedure to DoD or other authorities. IT Manager was not aware of the DFARS 72-hour reporting requirement. |
| 3.6.3 | Test incident response capability | **NI** | EVD-IR-04 | **Gap:** No IR testing conducted. No tabletop exercises, functional drills, or simulations. |

**IR Summary:** 0 I, 0 PI, **3 NI**, 0 N/A, 0 Not Assessed

---

### 9. Maintenance (MA) — 4 Applicable Controls

| Req | Description | Rating | Evidence Summary | Rationale |
|:---:|-------------|:------:|------------------|-----------|
| 3.7.1 | Perform system maintenance | **PI** | EVD-MA-01, EVD-MA-02 | Regular patching is performed. Windows updates are applied monthly. **Gap:** No formal patch management policy. Patching is done when IT has time rather than on a defined schedule. NAS firmware updates are irregular. No maintenance records kept. |
| 3.7.2 | Control maintenance tools and personnel | **PI** | EVD-MA-03 | MSP contract exists with basic service level agreement. **Gap:** No security requirements are specified in the MSP contract. No background check requirement for MSP technicians. No restriction on data access. |
| 3.7.5 | Require MFA for nonlocal maintenance | **NI** | EVD-MA-04 | **Gap:** MSP remote maintenance does not consistently require MFA. Some MSP connections use password-only authentication via remote desktop. |
| 3.7.6 | Supervise maintenance personnel | **NI** | EVD-MA-05 | **Gap:** MSP activities are not supervised or logged. No monitoring of MSP sessions. No post-maintenance review. |

**MA Summary:** 0 I, 2 PI, 2 NI, 2 N/A, 0 Not Assessed

---

### 10. Media Protection (MP) — 7 Applicable Controls

| Req | Description | Rating | Evidence Summary | Rationale |
|:---:|-------------|:------:|------------------|-----------|
| 3.8.1 | Protect system media containing CUI | **PI** | EVD-MP-01, EVD-PE-02 | NAS is in locked server room. **Gap:** No formal media protection policy. Backup drives stored in same room as NAS — no off-site or fire-resistant storage. Printed CUI documents are not addressed in policy. |
| 3.8.2 | Limit access to CUI on media | **I** | EVD-MP-01, EVD-AC-02 | Access controls on NAS shares restrict CUI document access to authorized users only. |
| 3.8.3 | Control use of removable media | **PI** | EVD-MP-02, EVD-AC-12 | USB write restriction configured via GPO. **Gap:** Field laptops may have restrictions disabled. No policy addresses use of personal USB drives. |
| 3.8.4 | Prohibit ownerless portable storage | **NI** | EVD-MP-02 | **Gap:** No policy addressing ownerless portable media. Lost USB drives would not be handled consistently. |
| 3.8.5 | Sanitize or destroy media before disposal | **NI** | EVD-MP-04 | **Gap:** No media sanitization procedure. Old hard drives are stored in a closet — not sanitized or destroyed. No documented process for decommissioning equipment. |
| 3.8.8 | Control removable media for CUI transfer | **NI** | EVD-MP-02 | **Gap:** No controls on CUI transfer via removable media. If an employee copies CUI to a USB drive, there are no encryption or accountability controls. |
| 3.8.9 | Protect backup CUI confidentiality | **PI** | EVD-MP-03 | NAS backups are encrypted. **Gap:** OneDrive/Known Folder Move may back up CUI to cloud without explicit encryption verification. No backup testing or restoration drill documentation. |

**MP Summary:** 1 I, 3 PI, 3 NI, 2 N/A, 0 Not Assessed

---

### 11. Personnel Security (PS) — 2 Controls

| Req | Description | Rating | Evidence Summary | Rationale |
|:---:|-------------|:------:|------------------|-----------|
| 3.9.1 | Screen individuals prior to authorization | **PI** | EVD-PS-01, EVD-PS-02 | Background checks are conducted for all new hires. Records exist. **Gap:** No policy defining screening frequency for existing employees. Background check scope is basic (criminal only) — no credit or reference check for CUI-handling roles. |
| 3.9.2 | Protect systems during and after personnel actions | **PI** | EVD-PS-03, EVD-PS-04 | Termination checklist exists. HR notifies IT of terminations. **Gap:** Process is manual — accounts may remain active for days after termination if HR notification is delayed. No transfer process — role changes do not trigger access review. |

**PS Summary:** 0 I, 2 PI, 0 NI, 0 N/A, 0 Not Assessed

---

### 12. Physical Protection (PE) — 6 Controls

| Req | Description | Rating | Evidence Summary | Rationale |
|:---:|-------------|:------:|------------------|-----------|
| 3.10.1 | Limit physical access to systems | **I** | EVD-PE-01, EVD-PE-02, EVD-PE-06 | Server room locked with keypad. Only IT and Executive have access. Property offices are locked after hours. |
| 3.10.2 | Protect physical access to CUI assets | **I** | EVD-PE-02, EVD-PE-06 | NAS and file server in locked server room. Workstations in supervised office areas. Property office workstations in locked offices. |
| 3.10.3 | Escort visitors and monitor activity | **PI** | EVD-PE-03 | Visitors sign in at reception. **Gap:** No formal visitor escort policy. In practice, visitors are loosely supervised. No visitor badges. |
| 3.10.4 | Maintain physical access audit logs | **I** | EVD-PE-04 | Server room has keypad with access logs. Sign-in sheet at reception for general visitors. |
| 3.10.5 | Control and manage physical access devices | **I** | EVD-PE-01 | Keys and keypad codes are controlled. Key inventory exists. Keypad codes changed annually and upon termination. |
| 3.10.6 | Enforce safeguarding at alternate work sites | **NI** | EVD-PE-05 | **Gap:** No remote work physical security policy. Remote employees have no guidance on securing home office environments. No verification that remote work environments are secure. |

**PE Summary:** 4 I, 1 PI, 1 NI, 0 N/A, 0 Not Assessed

---

### 13. Risk Assessment (RA) — 3 Controls

| Req | Description | Rating | Evidence Summary | Rationale |
|:---:|-------------|:------:|------------------|-----------|
| 3.11.1 | Periodically assess risk | **NI** | EVD-RA-01, EVD-RA-02 | **Gap:** No formal risk assessment process. No risk assessment reports exist. This readiness assessment is the first risk assessment performed. |
| 3.11.2 | Scan for vulnerabilities | **NI** | EVD-RA-03 | **Gap:** No vulnerability scanning is performed. No scanning tools deployed. Patch levels are not verified beyond Windows Update. NAS, firewall, and network devices are not scanned. |
| 3.11.3 | Remediate vulnerabilities | **PI** | EVD-RA-04 | Windows updates are applied, though on an ad hoc schedule. **Gap:** Without vulnerability scanning (3.11.2), there is no systematic remediation. Remediation is reactive based on vendor notifications. |

**RA Summary:** 0 I, 1 PI, 2 NI, 0 N/A, 0 Not Assessed

---

### 14. Security Assessment (CA) — 6 Controls

| Req | Description | Rating | Evidence Summary | Rationale |
|:---:|-------------|:------:|------------------|-----------|
| 3.12.1 | Assess security controls on ongoing basis | **NI** | EVD-CA-03 | **Gap:** No continuous monitoring program. No regular control assessments. This readiness assessment is the first security assessment conducted. |
| 3.12.2 | Develop and implement POA&M | **NI** | EVD-CA-02 | **Gap:** No POA&M exists. No formal process for tracking remediation of security deficiencies. This assessment will generate the first POA&M. |
| 3.12.3 | Monitor security controls continuously | **NI** | EVD-CA-03 | **Gap:** No continuous monitoring. Controls are not monitored for ongoing effectiveness. No automated monitoring tools deployed. |
| 3.12.4 | Develop and update System Security Plan (SSP) | **NI** | EVD-CA-01 | **Gap:** No System Security Plan exists. This is a critical gap for DFARS compliance — the SSP is the primary documentation of how security requirements are implemented. |
| 3.12.5 | Plan and conduct security authorization | **NI** | EVD-CA-01, EVD-CA-04 | **Gap:** No security authorization process. No ATO or equivalent. System is operating without formal authorization. |
| 3.12.6 | Conduct periodic assessments | **PI** | EVD-CA-04 | **Gap:** No prior assessments conducted. This readiness assessment partially fulfills this requirement but ongoing periodic assessments are not established. |

**CA Summary:** 0 I, 1 PI, 5 NI, 0 N/A, 0 Not Assessed

---

### 15. System & Communications Protection (SC) — 17 Applicable Controls

| Req | Description | Rating | Evidence Summary | Rationale |
|:---:|-------------|:------:|------------------|-----------|
| 3.13.1 | Monitor and protect communications at boundaries | **I** | EVD-SC-01, EVD-SC-02 | Firewall at head office boundary. Basic rules in place. Egress and ingress filtering configured. |
| 3.13.2 | Employ architectural designs for security | **NI** | EVD-SC-01 | **Gap:** No documented security architecture. Network grew organically. No architecture principles applied. No defense-in-depth design evident. |
| 3.13.3 | Separate user and system management functionality | **I** | EVD-AC-13, EVD-SC-01 | Admin interfaces are separate from user interfaces. Standard users cannot access admin consoles. |
| 3.13.4 | Prevent unauthorized transfer via shared resources | **I** | EVD-CM-04 | User isolation on shared systems is adequate. No multi-tenant virtualization concerns. |
| 3.13.5 | Implement subnetworks for public-facing systems | **I** | EVD-SC-06, EVD-SC-07 | Guest Wi-Fi on separate VLAN. No public-facing servers requiring DMZ (no web servers, no public apps). |
| 3.13.6 | Deny by default, permit by exception | **I** | EVD-SC-02 | Firewall has default-deny rule. Only required ports are permitted. No any/any rules. |
| 3.13.7 | Prevent split-tunneling | **NI** | EVD-SC-10 | **Gap:** VPN is configured for split-tunneling. Remote users can access the internet directly while connected to VPN. This bypasses the org firewall for internet-bound traffic. |
| 3.13.8 | Encrypt CUI during transmission | **PI** | EVD-SC-03, EVD-SC-05 | VPN uses AES-256. M365 uses TLS 1.2. **Gap:** PM SaaS encryption standard not confirmed. Some internal network traffic (NAS to workstations on LAN) may not be encrypted. |
| 3.13.9 | Terminate network connections after inactivity | **PI** | EVD-SC-11 | VPN idle timeout configured (30 min). **Gap:** M365 web app sessions do not have enforced timeout. PM SaaS session timeout not confirmed. |
| 3.13.10 | Establish and manage cryptographic keys | **PI** | EVD-SC-03, EVD-SC-05 | BitLocker recovery keys backed up to AD. VPN certificates managed. **Gap:** No formal key management policy. PM SaaS encryption keys managed by vendor — no visibility. |
| 3.13.11 | Employ FIPS-validated cryptography | **I** | EVD-SC-05 | VPN uses FIPS 140-2 validated module. BitLocker uses FIPS-compliant algorithm. |
| 3.13.12 | Prohibit remote activation of collaborative devices | **I** | EVD-CM-03, EVD-CM-04 | Remote activation of webcams/mics is not configured. Physical webcam covers observed on field laptops. |
| 3.13.14 | Protect CUI at rest | **PI** | EVD-SC-04 | **CRITICAL FINDING.** Company laptops have BitLocker (verified on sample). **Gap:** NAS is NOT encrypted. Server room physical access compensates but data at rest on NAS is unprotected. PM SaaS encryption at rest not confirmed. |
| 3.13.15 | Protect CUI in system output | **PI** | EVD-PE-01, Observation | Printer locations are in supervised areas. **Gap:** No clean desk policy enforced. CUI documents observed on desks during walkthrough. No shredding policy for CUI documents. |
| 3.13.17 | Implement architecture for traffic visibility | **PI** | EVD-SC-08, EVD-AU-03 | M365 audit logging provides cloud traffic visibility. **Gap:** No network monitoring or traffic analysis tool. Internal traffic east-west visibility is limited. No ability to detect lateral movement. |
| 3.13.18 | Implement architecture for traffic control | **I** | EVD-SC-02, EVD-SC-06 | Firewall controls north-south traffic. VLAN segmentation controls lateral traffic between zones. |
| 3.13.19 | Limit use of non-organizationally owned systems | **NI** | EVD-AC-08, EVD-SC-08 | **Gap:** BYOD policy exists but is not enforced. Personal devices access corporate email and potentially CUI without compliance requirements. No MAM/Conditional Access policies restrict CUI access from personal devices. |

**SC Summary:** 9 I, 5 PI, 3 NI, 2 N/A, 0 Not Assessed

---

### 16. System & Information Integrity (SI) — 7 Controls

| Req | Description | Rating | Evidence Summary | Rationale |
|:---:|-------------|:------:|------------------|-----------|
| 3.14.1 | Identify, report, and correct system flaws | **PI** | EVD-SI-03 | Windows updates applied monthly. **Gap:** No formal patch management policy. Third-party software patching is inconsistent. No flaw tracking system. |
| 3.14.2 | Provide protection from malicious code | **I** | EVD-SI-01, EVD-SI-02 | Antivirus/EDR installed on all company-managed endpoints. Real-time protection enabled. Signatures update automatically. |
| 3.14.3 | Monitor security alerts and advisories | **PI** | EVD-SI-06 | IT Manager subscribes to CISA alerts and vendor notifications. **Gap:** No formal process for triaging and acting on advisories. Responses are ad hoc. |
| 3.14.4 | Update malicious code protection mechanisms | **I** | EVD-SI-02 | AV/EDR signature updates are automatic. Verified current on sample endpoints. |
| 3.14.5 | Perform periodic and real-time scans | **I** | EVD-SI-02, EVD-SI-04 | Real-time scanning enabled on all endpoints. Weekly scheduled scans configured. |
| 3.14.6 | Monitor for unusual or unauthorized activity | **PI** | EVD-SI-05 | M365 audit logging captures activity. EDR provides detection capabilities. **Gap:** No 24/7 monitoring. Alerts are reviewed during business hours only. No dedicated security monitoring staff. |
| 3.14.7 | Identify unauthorized use of systems | **PI** | EVD-AU-04, EVD-SI-05 | Account management processes exist. **Gap:** No proactive identification of unauthorized use. Detection relies on users reporting suspicious activity. |

**SI Summary:** 3 I, 4 PI, 0 NI, 0 N/A, 0 Not Assessed

---

### 17. Controls with Insufficient Evidence

The following controls could not be fully assessed due to evidence limitations:

| Req | Reason for Insufficient Evidence | Recommended Action |
|:---:|---------------------------------|-------------------|
| AC 3.1.22 | Unable to verify JIT/PAM configuration — no system access | Request MSP console access or documentation |
| IA 3.5.4 | NTLMv1 status not confirmed | Run NTLM audit script against domain |
| SC 3.13.9 | PM SaaS timeout not configurable by client | Request vendor documentation |
| SC 3.13.10 | No formal key management — evidence collection needed | Interview IT on current key storage practices |
| SC 3.13.15 | Clean desk policy — observation limited to one site | Schedule follow-up observation |
| MA 3.7.2 | MSP contract not provided despite request | Escalate to Executive Sponsor |
| MA 3.7.5 | MSP MFA not confirmed | Schedule direct technical verification with MSP |
| PS 3.9.1 | Background check records limited to sample | Request full records for all CUI-handling staff |
| MP 3.8.9 | OneDrive encryption status not verified | Check M365 encryption settings |

---

### 18. Key Observations

| Observation | Severity | Affected Families |
|-------------|:--------:|:-----------------:|
| **No SSP or POA&M exists** — These are foundational DFARS compliance documents. Without them, the organization cannot demonstrate compliance. | **Critical** | CA |
| **No Incident Response Plan** — DFARS requires 72-hour incident reporting to DoD. Without an IR plan, the organization cannot meet this obligation. | **Critical** | IR |
| **No MFA on VPN or key services** — MFA is only partially deployed. VPN, PM SaaS, and MSP access lack MFA. | **High** | IA, AC, MA |
| **NAS is not encrypted** — The primary CUI repository has no encryption at rest. | **High** | SC, MP |
| **Logging exists but is not reviewed** — Audit logs are generated but never examined. | **High** | AU, IR |
| **BYOD is uncontrolled** — Personal devices access corporate data with no management or compliance enforcement. | **High** | AC, SC |
| **No vulnerability scanning** — The organization has no visibility into system vulnerabilities. | **High** | RA, SI |
| **Split-tunneling VPN** — Remote user traffic bypasses the org firewall. | **Medium** | SC |
| **No segregation of duties for IT** — IT staff use single accounts for all activities. | **Medium** | AC |
| **No data classification or CUI marking** — Employees cannot distinguish CUI from non-CUI data. | **Medium** | AC, AT |

---

### 19. Compliance Score Calculation

| Formula | Value |
|---------|:-----:|
| Total applicable controls | 107 |
| Implemented (I) | 57 |
| Compliance Score | **57 / 107 = 53%** |
| Implemented + Partially Implemented | 57 + 23 = 80 |
| Adjusted Score (with PI) | **80 / 107 = 75%** |

**Note:** A PI rating means gaps exist. For a third-party assessment or CMMC certification, PI is typically counted as a gap unless all PI items are remediated.

---

*Document Version: 1.0*
*Date: July 20, 2026*
