# Audit Checklist

## Confidential — NIST SP 800-171 Readiness Assessment

---

### 1. Purpose

This document is the primary field tool for assessing each applicable NIST SP 800-171 Rev 2 security requirement. It defines assessment criteria, evidence references, and test procedures for all 107 applicable requirements across 14 families.

**Assessment results are recorded directly in this document** and serve as the raw data for the Control Assessment (Phase 15) and Findings (Phase 16).

---

### 2. Rating Scale (Reference)

| Rating | Definition |
|--------|------------|
| **I** — Implemented | Control fully in place and operating as intended. Multiple sources confirm. |
| **PI** — Partially Implemented | Control exists but has gaps in coverage, documentation, or effectiveness. |
| **NI** — Not Implemented | Control does not exist or no evidence of implementation. |
| **N/A** — Not Applicable | Control does not apply; documented rationale exists. |

---

### 3. Access Control (AC)

#### 3.1.1 — Limit system access to authorized users, processes, and devices

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | User accounts are unique, managed through centralized directory (AD/Azure AD). No shared accounts. Device authentication is enforced. Periodic access reviews occur. |
| **Evidence References** | EVD-AC-01 (Access Control Policy), EVD-AC-02 (User Access List), EVD-AC-13 (Admin vs User Accounts) |
| **Test Procedures** | 1. Review access control policy for account management provisions. 2. Obtain user access list from AD/M365. 3. Verify no shared or generic accounts exist. 4. Interview IT Manager on account provisioning/deprovisioning process. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.1.2 — Limit system access to authorized transactions and functions

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Role-based access control (RBAC) is implemented. Users have access only to systems and functions required for their role. Privileged functions are restricted. |
| **Evidence References** | EVD-AC-01, EVD-AC-03 (RBAC Matrix) |
| **Test Procedures** | 1. Review RBAC matrix or equivalent access documentation. 2. Verify access aligns with job responsibilities. 3. Sample 3 user accounts and review their access rights. 4. Interview Property Manager on system access. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.1.3 — Control the flow of CUI in accordance with approved authorizations

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Data classification policy exists. CUI is identified and labeled. Data flow restrictions are enforced (no unauthorized transmission of CUI). Information flow control mechanisms (DLP, sharing restrictions) are implemented. |
| **Evidence References** | EVD-AC-01, EVD-SC-08 (M365 Conditional Access/DLP) |
| **Test Procedures** | 1. Review data classification policy. 2. Check M365 DLP and external sharing settings. 3. Verify SharePoint external sharing is restricted. 4. Interview on how CUI flow is managed. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.1.4 — Separate duties to reduce risk of malevolent activity

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Segregation of duties is documented and enforced where feasible given organizational size. No single individual has unchecked control over critical functions (e.g., IT admin should not also be the sole approver of their own changes). |
| **Evidence References** | EVD-AC-01 |
| **Test Procedures** | 1. Review policy for segregation of duties provisions. 2. Interview IT Manager and Exec on how duties are separated. 3. Note: 20-person org — full segregation may be impractical; compensating controls (audit logging, management oversight) are acceptable. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.1.5 — Employ the principle of least privilege

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Users have minimum permissions needed to perform their role. Privileged accounts are limited. Admin rights are not granted to standard users. |
| **Evidence References** | EVD-AC-03 (RBAC Matrix), EVD-AC-13 (Admin vs User Account Separation) |
| **Test Procedures** | 1. Review list of users with admin/privileged access. 2. Verify count is limited. 3. Check if standard users have local admin rights on their workstations. 4. Interview IT on how least privilege is enforced. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.1.6 — Use non-privileged accounts for non-security functions

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | IT administrators have separate user accounts for non-administrative activities (email, browsing). They do not browse the web or check email as admin. |
| **Evidence References** | EVD-AC-13 |
| **Test Procedures** | 1. Interview IT Manager on whether separate admin and user accounts are used. 2. Verify in AD/Azure AD that IT staff have two accounts (or equivalent privileged access management). |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.1.7 — Prevent non-privileged users from executing privileged functions

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Standard users cannot escalate privileges. UAC is enabled. No unauthorized privilege elevation paths exist. |
| **Evidence References** | EVD-AC-13, EVD-CM-04 (Workstation Configuration) |
| **Test Procedures** | 1. Verify UAC is enabled on sample workstation. 2. Verify standard users are not in local admin group. 3. Review GPO for user rights assignments. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.1.8 — Limit unsuccessful logon attempts

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Account lockout policy is configured (e.g., 5-10 failed attempts triggers lockout for 15+ minutes). Lockout duration and reset timer are defined. |
| **Evidence References** | EVD-AC-10 (Account Lockout Configuration) |
| **Test Procedures** | 1. Review GPO or equivalent for account lockout threshold, lockout duration, and reset counter. 2. Verify against policy. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.1.9 — Provide privacy and security notices

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Logon banner is displayed before access is granted to systems containing CUI. Banner includes appropriate legal notice and warning about unauthorized access. |
| **Evidence References** | EVD-AC-11 (Logon Banner Configuration) |
| **Test Procedures** | 1. Review GPO for interactive logon message text and title. 2. Verify banner is displayed on sample workstation during logon. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.1.10 — Use session lock with pattern-hiding displays

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Workstations and laptops automatically lock after 15 minutes of inactivity (or less). Screen saver is enabled with password protection. |
| **Evidence References** | EVD-AC-09 (Session Lock Configuration) |
| **Test Procedures** | 1. Review GPO for screen saver timeout, lock on resume. 2. Verify on sample workstation by observing screen lock behavior. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.1.11 — Terminate sessions automatically after defined conditions

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Remote access sessions (VPN, cloud apps) automatically terminate after inactivity. Web app sessions have timeout. VPN idle disconnect is configured. |
| **Evidence References** | EVD-AC-09, EVD-SC-11 (Session Termination) |
| **Test Procedures** | 1. Review VPN configuration for idle timeout. 2. Check M365 Conditional Access session controls. 3. Verify PM SaaS session timeout setting (if configurable). |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.1.12 — Monitor and control remote access sessions

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Remote access is authorized, logged, and monitored. Only authorized users can establish remote access. VPN access requires authentication. |
| **Evidence References** | EVD-AC-04 (Remote Access Policy), EVD-AC-05 (VPN Config) |
| **Test Procedures** | 1. Review remote access policy. 2. Verify VPN authentication method. 3. Review VPN connection logs for unauthorized attempts. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.1.13 — Encrypt remote access sessions

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Remote access sessions are encrypted using FIPS-validated cryptography. VPN uses strong encryption (AES-256 or equivalent). |
| **Evidence References** | EVD-AC-05 (VPN Config), EVD-SC-03 (Encryption Config) |
| **Test Procedures** | 1. Review VPN encryption configuration. 2. Verify protocol and cipher strength. 3. Confirm FIPS 140-2 validation. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.1.14 — Route remote access via managed access control points

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Remote access to internal systems must go through the VPN/firewall. Direct RDP to internal systems from the internet is prohibited. |
| **Evidence References** | EVD-AC-05, EVD-SC-02 (Firewall Rule Set) |
| **Test Procedures** | 1. Review firewall rules for inbound remote access. 2. Verify no direct RDP/SSH ports are exposed to internet. 3. Note: direct-to-cloud access is a separate flow (covered under SC). |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.1.15 — Authorize remote execution of privileged commands

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Remote privileged access (admin tasks) requires authorization, MFA, and is logged. MSP admin access follows same rules. |
| **Evidence References** | EVD-AC-04, EVD-IA-02 (MFA), EVD-MA-04 (MSP MFA) |
| **Test Procedures** | 1. Interview IT Manager on how remote admin access is authorized. 2. Verify MFA is required for remote admin. 3. Review MSP access procedure. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.1.16 — Authorize wireless access prior to allowing connections

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Wi-Fi network requires authentication before granting access. Guest network is isolated from corporate network. |
| **Evidence References** | EVD-AC-06 (Wireless Configuration) |
| **Test Procedures** | 1. Review Wi-Fi configuration. 2. Verify WPA2/3 encryption. 3. Verify SSID segmentation (corporate vs. guest). |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.1.17 — Protect wireless access using authentication and encryption

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Wi-Fi uses enterprise authentication (802.1X) or strong pre-shared key with encryption. WEP is not used. |
| **Evidence References** | EVD-AC-06 |
| **Test Procedures** | 1. Verify wireless authentication method. 2. Confirm encryption is AES (not TKIP). 3. Ensure WEP is not in use. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.1.18 — Control connection of mobile devices

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Mobile device connection policy exists. BYOD is controlled through policy and technical controls (Conditional Access, MDM if applicable). |
| **Evidence References** | EVD-AC-07 (MDM Policy/Config), EVD-AC-08 (BYOD Policy) |
| **Test Procedures** | 1. Review mobile device policy. 2. Check M365 Conditional Access policies for mobile devices. 3. Verify MDM/MAM configuration (if deployed). |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.1.19 — Encrypt CUI on mobile devices

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Mobile devices that access CUI are encrypted at rest. Company laptops have full disk encryption. BYOD devices with CUI access require encryption through MAM policies. |
| **Evidence References** | EVD-AC-07, EVD-SC-04 (Encryption at Rest) |
| **Test Procedures** | 1. Verify BitLocker or FileVault on sample laptops. 2. Check M365 MAM policy for requiring device encryption. 3. Verify company mobile devices are encrypted (iOS/Android encryption enabled). |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.1.20 — Limit use of portable storage devices on external systems

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | USB ports are controlled via policy and technical restrictions. Removable media is not allowed on systems that process CUI unless authorized. |
| **Evidence References** | EVD-AC-12 (USB Restriction Config) |
| **Test Procedures** | 1. Review USB restriction policy. 2. Check GPO for removable storage access. 3. Verify USB write protection or blocking on sample workstation. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.1.21 — Control information posted on publicly accessible systems

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Process exists to review information before it is posted to public-facing systems (website). No CUI or PII is posted publicly. |
| **Evidence References** | EVD-AC-01 |
| **Test Procedures** | 1. Review public website for any inadvertent PII/CUI exposure. 2. Interview Admin on website content approval process. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.1.22 — Authorize remote execution of privileged commands (enhanced)

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Same as 3.1.15 with enhanced controls. Remote privileged commands require explicit authorization, MFA, and are logged with full session recording or detailed audit trail. |
| **Evidence References** | EVD-AC-04, EVD-IA-02, EVD-MA-04 |
| **Test Procedures** | 1. Same as 3.1.15. 2. Verify additional logging for privileged remote sessions. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

---

### 4. Awareness & Training (AT)

#### 3.2.1 — Security awareness training for all personnel

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | All personnel receive security awareness training at least annually. Training covers security risks, policies, and procedures. Training records are maintained. |
| **Evidence References** | EVD-AT-01 (Training Policy), EVD-AT-02 (Training Records), EVD-AT-05 (Training Schedule) |
| **Test Procedures** | 1. Review security awareness training policy. 2. Review training records (attendance, completion). 3. Interview 2-3 employees on what training they received. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.2.2 — Role-based training for security duties

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Personnel with specific security responsibilities (IT, CUI handlers) receive role-based training on their duties. |
| **Evidence References** | EVD-AT-03 (Role-Based Training Materials) |
| **Test Procedures** | 1. Review role-based training materials. 2. Interview IT Manager on whether specialized training is provided for CUI handling. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.2.3 — Insider threat awareness training

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Training includes recognition and reporting of insider threat indicators (unusual behavior, unauthorized data access, policy violations). |
| **Evidence References** | EVD-AT-04 (Insider Threat Training Materials) |
| **Test Procedures** | 1. Review insider threat training content. 2. Verify training covers reporting channels. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

---

### 5. Audit & Accountability (AU)

#### 3.3.1 — Create and retain system audit records

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Audit logging is enabled on all CUI-bearing systems (NAS, M365, firewall, endpoints). Logs are retained for a defined period (minimum 12 months recommended). |
| **Evidence References** | EVD-AU-01 (Audit Policy), EVD-AU-02 (Audit Config), EVD-AU-03 (Sample Logs) |
| **Test Procedures** | 1. Review audit policy. 2. Verify audit logging is enabled on NAS, M365, firewall. 3. Review sample logs for content completeness. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.3.2 — Ensure individual user actions can be uniquely traced

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | All users have unique accounts. Audit logs identify individual user actions. No shared accounts for interactive access. |
| **Evidence References** | EVD-AU-02, EVD-IA-04 (User Account List) |
| **Test Procedures** | 1. Verify all accounts are unique (no shared accounts). 2. Review sample logs to confirm user identities are recorded. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.3.3 — Review and update logged events

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Logs are reviewed on a regular basis. Review frequency is documented. Evidence of log review exists (review records, sign-offs). |
| **Evidence References** | EVD-AU-04 (Log Review Procedure) |
| **Test Procedures** | 1. Review log review procedure. 2. Ask for evidence of recent log reviews (emails, reports, sign-offs). 3. Interview IT on how often logs are reviewed. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.3.4 — Alert on audit logging process failure

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Alerting is configured for audit log failures (disk full, logging service stopped). IT is notified when logging fails. |
| **Evidence References** | EVD-AU-07 (Log Alerting Configuration) |
| **Test Procedures** | 1. Review alerting configuration for audit log failures. 2. Interview IT on how they would know if logging stopped. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.3.5 — Correlate audit record review for investigation

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Log review includes correlation across systems. Incident investigation uses correlated logs. Process exists to identify suspicious activity across multiple sources. |
| **Evidence References** | EVD-AU-04, EVD-IR-01 (IR Plan) |
| **Test Procedures** | 1. Interview IT on how logs are correlated during incident investigation. 2. Review any SIEM or log aggregation tool (if exists). |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.3.6 — Provide audit record reduction and report generation

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Capability exists to generate audit reports from logs. Report generation supports on-demand analysis. |
| **Evidence References** | EVD-AU-01, EVD-AU-04 |
| **Test Procedures** | 1. Ask IT to demonstrate log report generation. 2. Review available reporting capabilities (M365 audit log search, firewall logs, etc.). |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.3.7 — Synchronize internal clocks with authoritative source

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | All systems use NTP to synchronize time with an authoritative source. Timestamps in logs are consistent across systems. |
| **Evidence References** | EVD-AU-06 (NTP Configuration) |
| **Test Procedures** | 1. Review NTP configuration on NAS, firewall, workstations. 2. Compare timestamps across logs from different systems. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.3.8 — Protect audit information from unauthorized access

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Audit logs are protected from unauthorized access, modification, and deletion. Only authorized personnel can access logs. Logs are stored in a location separate from the systems being monitored (or access is restricted). |
| **Evidence References** | EVD-AU-05 (Log Protection) |
| **Test Procedures** | 1. Review who has access to audit logs. 2. Verify access controls on log storage. 3. Check if logs are append-only or immutable (if applicable). |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.3.9 — Limit audit logging management to privileged users

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Only authorized privileged users can configure audit logging settings. Standard users cannot disable or modify logging. |
| **Evidence References** | EVD-AU-05 |
| **Test Procedures** | 1. Review permissions for audit log configuration. 2. Verify that non-admin users cannot modify audit settings. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

---

### 6. Configuration Management (CM)

#### 3.4.1 — Establish baseline configurations and inventories

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Baseline configurations exist for all in-scope systems (workstations, servers, network devices). Hardware and software inventories are maintained. |
| **Evidence References** | EVD-CM-01 (Baseline Config), EVD-CM-08 (Software Inventory) |
| **Test Procedures** | 1. Review baseline configuration documents. 2. Compare against actual systems (sample). 3. Review hardware and software inventory. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.4.2 — Establish and enforce security configuration settings

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Security hardening standards are applied (CIS Benchmarks, STIGs, or equivalent). Workstations and servers are configured per standard. |
| **Evidence References** | EVD-CM-03 (Hardening Standards), EVD-CM-04 (Sample Workstation Config) |
| **Test Procedures** | 1. Review hardening standard used. 2. Verify hardening settings on sample workstation (password req, audit, firewall, etc.). |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.4.3 — Track, review, and log changes

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Change management process exists. Changes are tracked, reviewed, approved/rejected, and logged. |
| **Evidence References** | EVD-CM-05 (Change Management Policy), EVD-CM-06 (Change Records) |
| **Test Procedures** | 1. Review change management policy. 2. Review recent change request records. 3. Interview IT on how changes are managed. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.4.4 — Analyze security impact of changes prior to implementation

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Security impact analysis is performed for significant changes before implementation. |
| **Evidence References** | EVD-CM-05, EVD-CM-06 |
| **Test Procedures** | 1. Review change records for evidence of security impact analysis. 2. Interview IT on how they assess security impact of changes. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.4.5 — Define and enforce access restrictions for changes

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Physical and logical access restrictions are defined and enforced for system changes. Only authorized personnel can make changes. |
| **Evidence References** | EVD-CM-05 |
| **Test Procedures** | 1. Review who is authorized to make system changes. 2. Verify access controls prevent unauthorized changes. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.4.6 — Employ least functionality

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Systems are configured to provide only essential capabilities. Unnecessary services, protocols, and programs are disabled. |
| **Evidence References** | EVD-CM-03, EVD-CM-04 |
| **Test Procedures** | 1. Review sample workstation for unnecessary services. 2. Check for unnecessary open ports. 3. Review server configuration for minimal services. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.4.7 — Restrict use of nonessential programs and services

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Nonessential programs, functions, ports, protocols, and services are restricted or disabled. |
| **Evidence References** | EVD-CM-07 (Software Restriction) |
| **Test Procedures** | 1. Review software restriction policy/configuration. 2. Verify unauthorized software cannot be installed. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.4.8 — Apply deny-by-exception policy

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Deny-by-exception (blacklisting) or allow-by-exception (whitelisting) is implemented for software execution. |
| **Evidence References** | EVD-CM-07 |
| **Test Procedures** | 1. Determine whether whitelisting or blacklisting is used. 2. Verify effectiveness of the approach in use. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.4.9 — Control and monitor user-installed software

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Standard users cannot install software without authorization. User-installed software is monitored and controlled. |
| **Evidence References** | EVD-CM-07 |
| **Test Procedures** | 1. Verify standard users are not local admins. 2. Check if software installation is blocked via GPO. 3. Interview IT on how software installation is controlled. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

---

### 7. Identification & Authentication (IA)

#### 3.5.1 — Identify system users, processes, and devices

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | All users, processes acting on behalf of users, and devices are uniquely identified. Identification occurs before authentication. |
| **Evidence References** | EVD-IA-01 (I&A Policy), EVD-IA-04 (User Account List), EVD-IA-05 (Service Accounts) |
| **Test Procedures** | 1. Review user account list. 2. Verify service accounts are identified and managed. 3. Verify device identification exists (AD computer objects, device registration). |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.5.2 — Authenticate identities prior to access

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Authentication is required before any access to organizational systems is granted. Anonymous access is prohibited. |
| **Evidence References** | EVD-IA-01, EVD-AC-01 |
| **Test Procedures** | 1. Verify authentication is enforced for all system access. 2. Check for any anonymous or guest access enabled. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.5.3 — Use multifactor authentication (MFA)

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | MFA is required for: (a) network access to privileged accounts, (b) network access to non-privileged accounts. MFA is enforced for remote access, cloud admin, and all M365 access. |
| **Evidence References** | EVD-IA-02 (MFA Configuration) — **Critical Evidence** |
| **Test Procedures** | 1. Review MFA configuration in M365 / Azure AD. 2. Verify MFA is enforced for all users (not optional). 3. Check VPN MFA configuration. 4. Confirm PM SaaS supports and requires MFA. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.5.4 — Employ replay-resistant authentication

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Authentication protocols are resistant to replay attacks. Kerberos, modern authentication (OAuth/SAML), and secure protocols are used. NTLMv1 is disabled. |
| **Evidence References** | EVD-IA-07 (Replay Resistance) |
| **Test Procedures** | 1. Verify NTLMv1 is disabled. 2. Confirm Kerberos is primary authentication protocol. 3. Verify modern auth is enabled for M365. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.5.5 — Prevent reuse of identifiers for 5 years

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Once a user identifier is deactivated, it is not reused for at least 5 years. Process exists to prevent identifier reuse. |
| **Evidence References** | EVD-IA-01 |
| **Test Procedures** | 1. Review account management policy for identifier reuse prohibition. 2. Interview IT on how terminated user accounts are handled. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.5.6 — Disable identifiers after inactivity

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Inactive user accounts are disabled after a defined period (e.g., 35-90 days). |
| **Evidence References** | EVD-IA-01, EVD-IA-04 |
| **Test Procedures** | 1. Check for accounts that have been inactive for extended periods. 2. Verify inactive account disabling policy exists. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.5.7 — Enforce minimum password complexity and character changes

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Password policy enforces minimum length (14+ characters recommended), complexity (uppercase, lowercase, numbers, special characters), minimum/maximum age. |
| **Evidence References** | EVD-IA-03 (Password Policy Config) |
| **Test Procedures** | 1. Review password policy GPO / Azure AD password settings. 2. Verify length, complexity, and age requirements are set. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.5.8 — Prohibit password reuse

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Password history is enforced. Users cannot reuse recent passwords (e.g., last 24 passwords). |
| **Evidence References** | EVD-IA-03 |
| **Test Procedures** | 1. Review password history setting. 2. Verify reuse threshold is configured. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.5.9 — Allow temporary passwords with immediate change

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Temporary passwords (for new accounts, password resets) require immediate change at next logon. |
| **Evidence References** | EVD-IA-06 (Temporary Password Procedure) |
| **Test Procedures** | 1. Verify "User must change password at next logon" is set for new accounts. 2. Review temporary password issuance process. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

---

### 8. Incident Response (IR)

#### 3.6.1 — Establish incident-handling capability

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Incident Response Plan exists and covers preparation, detection, analysis, containment, recovery, and user response. Plan includes DFARS 72-hour reporting requirement. |
| **Evidence References** | EVD-IR-01 (IR Plan) — **Critical Evidence**, EVD-IR-02 (Procedures/Playbooks), EVD-IR-05 (Incident History) |
| **Test Procedures** | 1. Review IR Plan. 2. Verify plan covers all phases. 3. Confirm DFARS reporting requirements are included. 4. Interview IT on their understanding of IR procedures. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.6.2 — Track, document, and report incidents

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Incidents are tracked in a log or ticket system. Documentation includes date, description, actions taken, and outcome. Reporting to appropriate authorities (including DoD) occurs per requirements. |
| **Evidence References** | EVD-IR-03 (Incident Reporting Process) |
| **Test Procedures** | 1. Review incident reporting procedures. 2. Ask for past incident records (if any). 3. Verify DoD reporting process is documented. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.6.3 — Test incident response capability

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | IR capability is tested at least annually. Testing can be tabletop exercise, functional drill, or full simulation. Results are documented and used to improve the plan. |
| **Evidence References** | EVD-IR-04 (IR Test Records) |
| **Test Procedures** | 1. Review IR test records. 2. Interview on last test date, scope, and lessons learned. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

---

### 9. Maintenance (MA)

#### 3.7.1 — Perform system maintenance

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Scheduled maintenance is performed. Patching is regular and documented. Maintenance records are kept. |
| **Evidence References** | EVD-MA-01 (Maintenance Policy), EVD-MA-02 (Patch Records) |
| **Test Procedures** | 1. Review maintenance/patch management policy. 2. Review patch records for last 6 months. 3. Verify patch levels on sample workstations. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.7.2 — Control maintenance tools and personnel

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Maintenance tools, techniques, mechanisms, and personnel are controlled. Third-party maintenance (MSP) has defined security requirements in contract. |
| **Evidence References** | EVD-MA-03 (MSP Agreement/SLA) |
| **Test Procedures** | 1. Review MSP contract for security requirements. 2. Verify maintenance tools are authorized and controlled. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.7.3 — N/A (No off-site maintenance)

| Field | Detail |
|-------|--------|
| **Result** | ☐ N/A |
| **Observations** | No equipment removed for off-site maintenance. All maintenance performed on-site or remotely. |

#### 3.7.4 — N/A (No diagnostic media)

| Field | Detail |
|-------|--------|
| **Result** | ☐ N/A |
| **Observations** | Diagnostic media is not part of standard operations. |

#### 3.7.5 — Require MFA for nonlocal maintenance

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | MFA is required for remote maintenance sessions (MSP, vendor). Sessions are terminated when maintenance is complete. |
| **Evidence References** | EVD-MA-04 (MSP MFA Evidence) |
| **Test Procedures** | 1. Interview IT on how MSP connects for maintenance. 2. Verify MFA is required. 3. Review session termination procedures. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.7.6 — Supervise maintenance personnel

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Maintenance activities by non-privileged personnel (or external parties) are supervised or logged. |
| **Evidence References** | EVD-MA-05 (Maintenance Log/Supervision) |
| **Test Procedures** | 1. Interview IT on how MSP maintenance is supervised. 2. Review maintenance logs for evidence of supervision. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

---

### 10. Media Protection (MP)

#### 3.8.1 — Protect system media containing CUI

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Physical and digital media containing CUI are physically controlled and securely stored. NAS is in a locked server room. Backups are stored securely. |
| **Evidence References** | EVD-MP-01 (Media Protection Policy), EVD-PE-02 (Server Room Observation) |
| **Test Procedures** | 1. Review media protection policy. 2. Observe server room physical security. 3. Verify backup media/destination is secured. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.8.2 — Limit access to CUI on media to authorized users

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Access controls on file shares, backup media, and removable media restrict access to authorized users only. |
| **Evidence References** | EVD-MP-01, EVD-AC-02 (User Access List) |
| **Test Procedures** | 1. Review access controls on NAS shares. 2. Verify only authorized users have access to CUI shares. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.8.3 — Control use of removable media

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Removable media (USB drives, external hard drives) use is controlled through policy and technical restrictions. |
| **Evidence References** | EVD-MP-02 (Removable Media Policy), EVD-AC-12 (USB Restriction Config) |
| **Test Procedures** | 1. Review removable media policy. 2. Verify USB restrictions are in place via GPO. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.8.4 — Prohibit use of ownerless portable storage

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Portable storage devices without an identifiable owner are prohibited from use. Lost or unlabeled devices are not connected to organizational systems. |
| **Evidence References** | EVD-MP-02 |
| **Test Procedures** | 1. Review policy on ownerless media. 2. Interview IT on how lost USB devices are handled. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.8.5 — Sanitize or destroy media before disposal

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Media containing CUI is sanitized (NIST SP 800-88) or destroyed before disposal or reuse. Procedure exists. |
| **Evidence References** | EVD-MP-04 (Media Sanitization Procedure) |
| **Test Procedures** | 1. Review media sanitization procedure. 2. Ask for records of past media sanitization/destruction. 3. Verify procedure aligns with NIST SP 800-88. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.8.6 — N/A (No media transport)

| Field | Detail |
|-------|--------|
| **Result** | ☐ N/A |
| **Observations** | No physical media containing CUI is transported outside controlled areas. |

#### 3.8.7 — N/A (No media transport)

| Field | Detail |
|-------|--------|
| **Result** | ☐ N/A |
| **Observations** | See 3.8.6. No physical media transport occurs. |

#### 3.8.8 — Control use of removable media for CUI transfer

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | If removable media is used to transfer CUI, controls (encryption, access controls, tracking) are applied. |
| **Evidence References** | EVD-MP-02, EVD-MP-01 |
| **Test Procedures** | 1. Determine if removable media is used for CUI transfer. 2. If yes, verify encryption and tracking controls. 3. Interview on how CUI is transferred between systems. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.8.9 — Protect backup CUI confidentiality

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Backups containing CUI are encrypted at rest. Backup storage location is secured. Access to backups is restricted. |
| **Evidence References** | EVD-MP-03 (Backup Encryption) |
| **Test Procedures** | 1. Verify NAS backup encryption. 2. Verify M365 backup encryption (if using third-party backup). 3. Review access controls on backup storage. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

---

### 11. Personnel Security (PS)

#### 3.9.1 — Screen individuals before authorizing access

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Background screening is conducted for all personnel with access to CUI systems. Screening is commensurate with risk. |
| **Evidence References** | EVD-PS-01 (Screening Policy), EVD-PS-02 (Background Check Records) |
| **Test Procedures** | 1. Review screening policy. 2. Sample background check records for current employees with CUI access. 3. Verify screening was conducted before access was granted. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.9.2 — Protect systems during and after personnel actions

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Account deactivation/termination process exists. Access is revoked immediately upon termination. Transfers result in updated access. Exit interviews include security reminder. |
| **Evidence References** | EVD-PS-03 (Termination/Transfer Procedure), EVD-PS-04 (Termination Evidence) |
| **Test Procedures** | 1. Review termination checklist/process. 2. Ask for recent termination records (redacted). 3. Verify accounts were disabled promptly. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

---

### 12. Physical Protection (PE)

#### 3.10.1 — Limit physical access to systems and equipment

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Physical access to systems (server room, network closet) is restricted to authorized personnel. Locked doors, access control, or equivalent. |
| **Evidence References** | EVD-PE-01 (Physical Security Policy), EVD-PE-02 (Server Room Observation), EVD-PE-06 (Property Office Observation) |
| **Test Procedures** | 1. Observe head office server room physical access controls. 2. Verify property office equipment is secured. 3. Review physical security policy. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.10.2 — Protect physical access to CUI assets

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | CUI assets (NAS, file server, workstations with CUI access) are in physically secure areas. |
| **Evidence References** | EVD-PE-02, EVD-PE-06 |
| **Test Procedures** | 1. Verify NAS is in locked server room. 2. Verify CUI workstations are in controlled access areas. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.10.3 — Escort visitors and monitor activity

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Visitors to secured areas are escorted or monitored. Visitor log is maintained. |
| **Evidence References** | EVD-PE-03 (Visitor Log/Procedure) |
| **Test Procedures** | 1. Review visitor management procedure. 2. Review visitor log. 3. Observe visitor handling practices. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.10.4 — Maintain physical access audit logs

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Physical access to sensitive areas is logged (electronic access logs or manual sign-in sheet). Logs are retained and reviewed. |
| **Evidence References** | EVD-PE-04 (Physical Access Logs) |
| **Test Procedures** | 1. Review physical access logs (electronic or manual). 2. Verify logs are retained for defined period. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.10.5 — Control and manage physical access devices

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Physical access devices (keys, key cards, fobs) are inventoried, controlled, and recovered upon termination. |
| **Evidence References** | EVD-PE-01 |
| **Test Procedures** | 1. Interview Admin on key/fob control process. 2. Verify keys are inventoried. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.10.6 — Enforce safeguarding measures at alternate work sites

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Remote workers have documented physical safeguarding requirements for CUI (locked doors, privacy screens, device security). |
| **Evidence References** | EVD-PE-05 (Remote Worker Policy) |
| **Test Procedures** | 1. Review remote work policy for physical security requirements. 2. Interview remote worker sample on their home office setup. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

---

### 13. Risk Assessment (RA)

#### 3.11.1 — Periodically assess risk

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Risk assessment process exists. Organizational-level risk assessments are performed periodically. Results are documented and reviewed. |
| **Evidence References** | EVD-RA-01 (Risk Assessment Policy), EVD-RA-02 (Previous RA Reports) |
| **Test Procedures** | 1. Review risk assessment policy. 2. Ask for previous risk assessment reports (if any). 3. Interview Exec on risk management approach. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.11.2 — Scan for vulnerabilities

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Vulnerability scanning is performed on organizational systems periodically and when new vulnerabilities are identified. |
| **Evidence References** | EVD-RA-03 (Vulnerability Scan Results) |
| **Test Procedures** | 1. Request recent vulnerability scan results. 2. Determine scanning frequency. 3. Verify scan coverage includes all in-scope systems. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.11.3 — Remediate vulnerabilities

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Vulnerabilities are remediated based on risk. Critical/high severity vulnerabilities have defined remediation timelines. Patch management process exists. |
| **Evidence References** | EVD-RA-04 (Remediation/Patch Records) |
| **Test Procedures** | 1. Review vulnerability remediation process. 2. Sample scan results and verify past findings have been remediated. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

---

### 14. Security Assessment (CA)

#### 3.12.1 — Assess security controls on an ongoing basis

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Continuous monitoring process exists. Security controls are assessed on an ongoing basis. |
| **Evidence References** | EVD-CA-03 (Continuous Monitoring Policy) |
| **Test Procedures** | 1. Review continuous monitoring policy. 2. Interview IT on what controls are monitored continuously. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.12.2 — Develop and implement POA&M

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Plan of Actions and Milestones (POA&M) exists for identified deficiencies. POA&M includes tasks, responsible parties, and target dates. |
| **Evidence References** | EVD-CA-02 (POA&M Document) |
| **Test Procedures** | 1. Review POA&M (if exists). 2. Verify it includes prioritized remediation tasks. 3. Note: this assessment will generate a POA&M. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.12.3 — Monitor security controls continuously

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Security controls are monitored on an ongoing basis to ensure continued effectiveness. Monitoring includes automated and manual methods. |
| **Evidence References** | EVD-CA-03 |
| **Test Procedures** | 1. Review monitoring tools and methods. 2. Interview IT on how they know controls are still working after initial implementation. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.12.4 — Develop and update System Security Plan (SSP)

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | SSP exists, describes system boundary, environment of operation, security requirement implementation, and interconnections. SSP is current and updated periodically. |
| **Evidence References** | EVD-CA-01 (SSP) — **Critical Evidence** |
| **Test Procedures** | 1. Review SSP (if exists). 2. Verify it addresses all required elements. 3. Note: if SSP does not exist, this is a major gap and a priority finding. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.12.5 — Plan and conduct security authorization

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Security authorization (ATO or equivalent) is planned and conducted. Senior official authorizes system operation based on risk. |
| **Evidence References** | EVD-CA-01, EVD-CA-04 (Previous Assessment Reports) |
| **Test Procedures** | 1. Review any prior authorization documentation. 2. Interview Exec on whether a formal authorization process exists. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.12.6 — Conduct periodic assessments

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Periodic assessments of security controls are conducted. Assessment results are documented and used to improve security posture. |
| **Evidence References** | EVD-CA-04 |
| **Test Procedures** | 1. Request previous assessment reports. 2. Verify previous findings were addressed. 3. Note: this assessment partially fulfills this requirement. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

---

### 15. System & Communications Protection (SC)

#### 3.13.1 — Monitor, control, and protect communications at boundaries

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Boundary protection is implemented at external and key internal boundaries. Firewall, segmentation, and access controls are in place. |
| **Evidence References** | EVD-SC-01 (Network Diagram), EVD-SC-02 (Firewall Rules) |
| **Test Procedures** | 1. Review network architecture diagram. 2. Review firewall rule set. 3. Verify boundary controls are effective. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.13.2 — Employ architectural designs for information security

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Security architecture principles (defense in depth, least privilege, secure segmentation) are applied in system design. |
| **Evidence References** | EVD-SC-01 (Network Diagram) |
| **Test Procedures** | 1. Review network architecture for security principles. 2. Assess whether architecture supports security requirements. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.13.3 — Separate user functionality from system management

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Administrative interfaces are separate from user interfaces. Admin functions are not accessible from standard user accounts. |
| **Evidence References** | EVD-AC-13, EVD-SC-01 |
| **Test Procedures** | 1. Verify admin functions require separate authentication. 2. Verify standard users cannot access admin interfaces. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.13.4 — Prevent unauthorized information transfer via shared resources

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Shared system resources (memory, disk, network) are protected from unauthorized information transfer between users/processes. |
| **Evidence References** | EVD-CM-04 |
| **Test Procedures** | 1. Review virtualization configuration (if applicable). 2. Verify user isolation on shared systems. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.13.5 — Implement subnetworks for publicly accessible systems

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Publicly accessible systems are in a separate subnet (DMZ) logically separated from internal networks. Guest Wi-Fi is isolated. |
| **Evidence References** | EVD-SC-06 (Segmentation Config), EVD-SC-07 (Guest Wi-Fi) |
| **Test Procedures** | 1. Review VLAN segmentation configuration. 2. Verify guest Wi-Fi is isolated from corporate LAN. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.13.6 — Deny network traffic by default, permit by exception

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Firewall rules are default-deny. Only explicitly permitted traffic is allowed. Rules are reviewed periodically. |
| **Evidence References** | EVD-SC-02 |
| **Test Procedures** | 1. Review firewall rule base. 2. Verify default-deny rule is present and active. 3. Check for overly permissive rules (any/any). |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.13.7 — Prevent split-tunneling for remote devices

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Remote devices are prevented from simultaneously connecting to organizational systems AND external networks via a non-org connection. Force full tunnel VPN or equivalent. |
| **Evidence References** | EVD-SC-10 (Split-Tunneling Policy) |
| **Test Procedures** | 1. Review VPN configuration for split-tunneling. 2. Verify VPN is configured for full tunnel (all traffic routes through org firewall). |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.13.8 — Implement encryption to prevent unauthorized CUI disclosure during transmission

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | CUI transmitted over any network is encrypted using FIPS-validated cryptography. HTTPS, TLS 1.2+, VPN encryption are enforced. |
| **Evidence References** | EVD-SC-03 (Encryption in Transit) — **Critical Evidence**, EVD-SC-05 (FIPS Validation) |
| **Test Procedures** | 1. Verify VPN uses AES-256 or equivalent. 2. Verify M365 TLS configuration. 3. Check PM SaaS encryption (TLS). 4. Verify FIPS 140-2/3 validation. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.13.9 — Terminate network connections after inactivity

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Network connections (VPN, cloud sessions) are terminated after a defined period of inactivity. |
| **Evidence References** | EVD-SC-11 (Session Termination) |
| **Test Procedures** | 1. Verify VPN idle timeout. 2. Check M365 Conditional Access session timeout. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.13.10 — Establish and manage cryptographic keys

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Cryptographic keys are managed throughout their lifecycle (generation, distribution, storage, destruction). Key management policy exists. |
| **Evidence References** | EVD-SC-03, EVD-SC-05 |
| **Test Procedures** | 1. Review encryption key management practices. 2. Interview IT on how encryption keys are stored and managed. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.13.11 — Employ FIPS-validated cryptography

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | All cryptographic modules used to protect CUI are FIPS 140-2/3 validated. |
| **Evidence References** | EVD-SC-05 (FIPS Validation Evidence) |
| **Test Procedures** | 1. Verify FIPS validation for VPN encryption. 2. Verify BitLocker/FileVault is FIPS-compliant. 3. Check M365 FIPS compliance. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.13.12 — Prohibit remote activation of collaborative computing devices

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Remote activation of webcams, microphones, and other collaborative computing devices is prohibited. Devices provide indication when in use (LED, on-screen indicator). |
| **Evidence References** | EVD-CM-03, EVD-CM-04 |
| **Test Procedures** | 1. Verify webcam/mic settings prevent remote activation. 2. Check for physical camera covers (observation). |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.13.13 — N/A (No VoIP)

| Field | Detail |
|-------|--------|
| **Result** | ☐ N/A |
| **Observations** | No enterprise VoIP system deployed. |

#### 3.13.14 — Protect confidentiality of CUI at rest

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | CUI stored on any system (NAS, workstations, laptops, cloud) is encrypted at rest. Full disk encryption on endpoints. Encryption on NAS. Cloud data encrypted by provider. |
| **Evidence References** | EVD-SC-04 (Encryption at Rest) — **Critical Evidence** |
| **Test Procedures** | 1. Verify BitLocker/FileVault on sample laptops/workstations. 2. Verify NAS encryption (volume encryption or share encryption). 3. Review M365 data at rest encryption. 4. Review PM SaaS encryption at rest (vendor documentation). |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.13.15 — Protect CUI in system output

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | CUI in system output (printers, displays, reports) is protected. Printers in secure areas. Display screens are positioned to prevent shoulder surfing. |
| **Evidence References** | EVD-PE-01, Observation |
| **Test Procedures** | 1. Observe printer locations. 2. Verify CUI documents are not left on printers. 3. Review display positioning. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.13.16 — N/A (No system design/development)

| Field | Detail |
|-------|--------|
| **Result** | ☐ N/A |
| **Observations** | No in-house system development. |

#### 3.13.17 — Implement security architecture for traffic visibility

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Security architecture provides visibility into traffic traversing the enterprise (north-south and east-west). Network monitoring, logging, or analysis tools exist. |
| **Evidence References** | EVD-SC-08 (M365 Defender/CA), EVD-AU-03 (Logs) |
| **Test Procedures** | 1. Review network monitoring capabilities. 2. Verify visibility into internal traffic. 3. Check M365 audit logging for visibility. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.13.18 — Implement security architecture for traffic control

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Security architecture provides ability to control traffic traversing the enterprise. Firewall rules, ACLs, segmentation policies exist. |
| **Evidence References** | EVD-SC-02, EVD-SC-06 |
| **Test Procedures** | 1. Review firewall rule base for control. 2. Verify segmentation controls exist. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.13.19 — Limit use of non-organizationally owned systems for CUI

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Personal devices (BYOD) are restricted from processing, storing, or transmitting CUI. Policy prohibits CUI on personal devices. Technical controls (MAM, Conditional Access) enforce restrictions. |
| **Evidence References** | EVD-AC-08 (BYOD Policy), EVD-SC-08 (Conditional Access) |
| **Test Procedures** | 1. Review BYOD policy for CUI restrictions. 2. Verify MAM/Conditional Access policies prevent CUI download to personal devices. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

---

### 16. System & Information Integrity (SI)

#### 3.14.1 — Identify, report, and correct system flaws

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Flaw identification and remediation process exists (patch management). Critical patches are applied within defined timeframe. |
| **Evidence References** | EVD-SI-03 (Patch Management Policy/Records) |
| **Test Procedures** | 1. Review patch management policy. 2. Review recent patch records. 3. Verify patch levels on sample systems. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.14.2 — Provide protection from malicious code

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Antivirus/EDR is installed on all endpoints. Real-time protection is enabled. Signature updates are current. |
| **Evidence References** | EVD-SI-01 (Malware Protection Policy), EVD-SI-02 (AV/EDR Config) |
| **Test Procedures** | 1. Review malware protection policy. 2. Verify AV/EDR is installed and current on sample endpoints. 3. Check last scan date and signature version. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.14.3 — Monitor security alerts and advisories

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Security alerts and advisories are monitored (CISA, vendor notifications, industry sources). Actions are taken in response. |
| **Evidence References** | EVD-SI-06 (Alert Subscription Evidence) |
| **Test Procedures** | 1. Interview IT on alert sources they monitor. 2. Ask for recent example of action taken in response to a security advisory. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.14.4 — Update malicious code protection mechanisms

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | AV/EDR signature updates are applied automatically or on a defined schedule. Definitions are current. |
| **Evidence References** | EVD-SI-02 |
| **Test Procedures** | 1. Verify signature update schedule. 2. Check last update date on sample endpoints. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.14.5 — Perform periodic and real-time scans

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Periodic scans (scheduled) and real-time scans (file access, downloads) are performed. Scan coverage includes all endpoints. |
| **Evidence References** | EVD-SI-02, EVD-SI-04 (Vulnerability Scan Results) |
| **Test Procedures** | 1. Verify scheduled scan is configured. 2. Verify real-time scanning is enabled. 3. Review scan history. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.14.6 — Monitor for unusual or unauthorized activity

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Systems are monitored for unusual or unauthorized activity. Monitoring includes inbound and outbound traffic. Alerts are generated and reviewed. |
| **Evidence References** | EVD-SI-05 (Monitoring/Alerting Evidence) |
| **Test Procedures** | 1. Review monitoring configuration. 2. Ask for examples of alerts generated. 3. Verify alert review process. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

#### 3.14.7 — Identify unauthorized use of systems

| Field | Detail |
|-------|--------|
| **Assessment Criteria** | Process exists to identify unauthorized system use. Account monitoring, log review, and user reporting mechanisms are in place. |
| **Evidence References** | EVD-AU-04, EVD-SI-05 |
| **Test Procedures** | 1. Interview IT on how they detect unauthorized access. 2. Review any past incidents of unauthorized use. |
| **Result** | ☐ I ☐ PI ☐ NI ☐ N/A |
| **Observations** | |

---

### 17. Summary

| Family | Total Applicable | Tested |
|--------|:----------------:|:------:|
| AC — Access Control | 22 | ☐ |
| AT — Awareness & Training | 3 | ☐ |
| AU — Audit & Accountability | 9 | ☐ |
| CM — Configuration Management | 9 | ☐ |
| IA — Identification & Authentication | 9 | ☐ |
| IR — Incident Response | 3 | ☐ |
| MA — Maintenance | 4 | ☐ |
| MP — Media Protection | 7 | ☐ |
| PS — Personnel Security | 2 | ☐ |
| PE — Physical Protection | 6 | ☐ |
| RA — Risk Assessment | 3 | ☐ |
| CA — Security Assessment | 6 | ☐ |
| SC — System & Communications Protection | 17 | ☐ |
| SI — System & Information Integrity | 7 | ☐ |
| **Total** | **107** | ☐ |

---

### 18. Instructions for Use

1. **Before assessment:** Print or load this checklist for field use.
2. **During assessment:** For each control, review evidence, perform test procedures, and record result.
3. **Observations:** Write free-text notes on what was found — specific configurations, interview quotes, evidence gaps.
4. **After assessment:** Transfer results to Control Assessment spreadsheet (Phase 15) and Findings document (Phase 16).
5. **Retain:** This completed checklist is an audit artifact and should be retained with assessment records.

---

*Document Version: 1.0*
*Date: July 13, 2026*
