# Technical Verification Plan

## Confidential — NIST SP 800-171 Readiness Assessment

---

### 1. Purpose

This document defines the technical verification procedures for assessing NIST SP 800-171 controls through direct system examination. Technical verification provides objective, irrefutable evidence of control implementation — or lack thereof.

**Scope:** All in-scope systems defined in the System Boundary document (Phase 5).
**Methodology:** Configuration review, log analysis, and observation — NOT penetration testing.

---

### 2. Verification Principles

| Principle | Description |
|-----------|-------------|
| **Minimal Intrusion** | Verification uses read-only access where possible. No system changes are made. |
| **Authorized Access Only** | All verification is performed with explicit authorization using provided accounts. |
| **Evidence Capture** | Every verification step produces captured evidence (screenshot, export, photograph) with timestamp. |
| **Sampling** | Where full population testing is impractical, representative samples are tested per the sampling methodology defined in Phase 10. |
| **Repeatability** | Procedures are documented such that another assessor could repeat the verification and obtain the same results. |

---

### 3. Network Infrastructure Verification

**Target:** Firewall (NET-FW-001), Managed Switch (NET-SW-001/002), Wi-Fi AP (NET-AP-001)
**IT Contact Required:** Yes — administrative access needed

| # | Verification Item | Procedure | Expected Result | Evidence | Controls |
|:-:|-------------------|-----------|-----------------|----------|:--------:|
| 3.1 | Firewall rule base review | Log into firewall admin console. Export or screenshot full rule set. Review for: default-deny rule, overly permissive rules (any/any), exposed management ports from internet. | Default-deny rule present and active. No any/any rules. Management interfaces not exposed to internet. | Screenshot or config export | SC 3.13.6, SC 3.13.1 |
| 3.2 | Inbound port exposure | Review firewall NAT/port forwarding rules. List all inbound ports exposed to internet. | No direct RDP (3389), SSH (22), or SMB (445) exposed. Only VPN ports and business-required services. | Screenshot of NAT rules | AC 3.1.14, SC 3.13.1 |
| 3.3 | VPN configuration — protocol and encryption | Review VPN configuration: protocol (IPSec/SSL), encryption algorithm, key exchange, authentication method. | AES-256 or equivalent. FIPS 140-2 validated. MFA required. | Screenshot of VPN settings | AC 3.1.13, SC 3.13.8, SC 3.13.11 |
| 3.4 | VPN idle timeout | Review VPN idle timeout setting. | Session terminates after defined inactivity period (15-30 min recommended). | Screenshot of timeout config | AC 3.1.11, SC 3.13.9 |
| 3.5 | Split-tunneling configuration | Check VPN configuration for split-tunneling setting. | Full tunnel enforced (all traffic routes through org firewall). | Screenshot of split-tunnel setting | SC 3.13.7 |
| 3.6 | Network segmentation / VLANs | Review switch VLAN configuration. Identify VLANs and their purposes (corporate, guest Wi-Fi, management, DMZ). | Corporate and guest networks are on separate VLANs. Inter-VLAN access is restricted by ACLs. | Screenshot of VLAN config | SC 3.13.5 |
| 3.7 | Guest Wi-Fi isolation | Review Wi-Fi AP configuration. Verify guest SSID is isolated from corporate LAN. | Guest SSID can access internet only. No access to corporate IP ranges. | Screenshot of SSID settings | SC 3.13.5 |
| 3.8 | Wi-Fi encryption and authentication | Review wireless security settings: encryption standard, authentication method. | WPA2/3 with AES. Enterprise (802.1X) or strong pre-shared key. No WEP. | Screenshot of wireless security | AC 3.1.17 |
| 3.9 | NTP configuration | Check NTP settings on firewall/router. Verify time source. | NTP configured with authoritative time source. | Screenshot of NTP config | AU 3.3.7 |
| 3.10 | Device firmware version | Check firmware version on firewall, switch, AP. | Firmware is current within vendor support lifecycle. | Screenshot of firmware version | MA 3.7.1, SI 3.14.1 |

---

### 4. Server / Storage Verification

**Target:** NAS / File Server (SRV-NAS-001)
**IT Contact Required:** Yes — administrative access needed

| # | Verification Item | Procedure | Expected Result | Evidence | Controls |
|:-:|-------------------|-----------|-----------------|----------|:--------:|
| 4.1 | OS version and patch level | Check OS version and recent patch history. | Within vendor support lifecycle. Patches applied within defined window. | Screenshot | MA 3.7.1, SI 3.14.1 |
| 4.2 | Share permissions — CUI share | Review access control list on CUI document share. | Only authorized users/groups have access. No Everyone/Anonymous access. | Screenshot of share permissions | AC 3.1.2, AC 3.1.5 |
| 4.3 | Audit logging configuration | Check audit logging status. Verify what events are logged (logon, file access, privilege use, policy changes). | Audit logging enabled. Success and failure events for relevant categories. | Screenshot of audit config | AU 3.3.1, AU 3.3.2 |
| 4.4 | Encryption at rest | Check if NAS volume encryption or file-level encryption is enabled. | Data at rest is encrypted (volume encryption or file encryption). | Screenshot of encryption config | SC 3.13.14 |
| 4.5 | Backup configuration and encryption | Review backup settings: destination, frequency, retention. Verify backup encryption. | Backups encrypted. Defined retention period. Backup destination secured. | Screenshot of backup config | MP 3.8.9 |
| 4.6 | Local admin accounts | List local administrator accounts on NAS. | Limited to IT personnel only. No default/unchanged passwords. | Screenshot | AC 3.1.5 |
| 4.7 | Unused services/ports | Check for running services and open ports. | Only required services are running. Unnecessary services disabled. | Screenshot or CLI output | CM 3.4.6 |

---

### 5. Endpoint Verification (Sampling)

**Target:** 8 workstations/laptops from the following categories:
- 2 Head office workstations (one admin, one standard user)
- 2 Property office workstations (one per property)
- 2 Field laptops (one construction, one other)
- 1 IT workstation
- 1 Executive workstation

**IT Contact Required:** Yes — local access or remote management tool

| # | Verification Item | Procedure | Expected Result | Evidence | Controls |
|:-:|-------------------|-----------|-----------------|----------|:--------:|
| 5.1 | OS version and patch level | Check Windows Update history or `winver`. | Supported OS version. Latest patches applied within defined window. | Screenshot | MA 3.7.1, SI 3.14.1 |
| 5.2 | Antivirus/EDR status | Check AV/EDR console or system tray. Verify real-time protection, signature date, last scan. | AV installed. Real-time protection ON. Signatures current (less than 24 hours old). | Screenshot of AV status | SI 3.14.2, SI 3.14.4 |
| 5.3 | Full disk encryption | Check BitLocker status: `manage-bde -status` or Control Panel. | BitLocker (or equivalent) enabled. Protection ON. | Screenshot of encryption status | SC 3.13.14 |
| 5.4 | Screen lock / timeout | Run `powercfg /requests` and check screen saver settings: Control Panel → Personalization → Lock Screen → Screen timeout settings. | Screen locks after 15 minutes or less of inactivity. Password required on wake. | Screenshot of timeout settings | AC 3.1.10 |
| 5.5 | Local admin rights | Check if user is local admin: `net localgroup administrators`. | Standard users are NOT local administrators. | Screenshot of group membership | AC 3.1.7, CM 3.4.9 |
| 5.6 | Password policy | Check local or domain password policy: `net accounts` or GPO result. | Min password length 14+. Complexity enabled. History 24+. | Screenshot | IA 3.5.7, IA 3.5.8 |
| 5.7 | Account lockout policy | Check lockout settings: `net accounts` or GPO result. | Lockout threshold: 5-10 attempts. Lockout duration: 15+ minutes. | Screenshot | AC 3.1.8 |
| 5.8 | Audit policy | Check audit policy: `auditpol /get /category:*`. | Relevant auditing categories enabled. | Screenshot | AU 3.3.1 |
| 5.9 | USB/removable media restrictions | Check GPO or registry for removable storage access. | USB write access restricted. Removable storage blocked or read-only. | Screenshot of GPO or reg key | AC 3.1.20, MP 3.8.3 |
| 5.10 | Screen saver password | Check "On resume, display logon screen" setting. | Password required to unlock workstation. | Screenshot | AC 3.1.10 |
| 5.11 | Logon banner | Check interactive logon message settings. | Legal notice displayed before logon. | Screenshot of banner | AC 3.1.9 |
| 5.12 | UAC status | Check User Account Control setting. | UAC is enabled (not disabled). | Screenshot | AC 3.1.7 |

---

### 6. Cloud Tenant Verification — Microsoft 365

**Target:** M365 Business Premium Tenant (CLOUD-M365)
**Access Required:** Global Admin or Security Admin role (read-only)

| # | Verification Item | Procedure | Expected Result | Evidence | Controls |
|:-:|-------------------|-----------|-----------------|----------|:--------:|
| 6.1 | MFA status for all users | Azure AD → Security → MFA → Per-user MFA status (or Conditional Access). | MFA is enforced for ALL users (not optional). Check for users with MFA disabled. | Screenshot of MFA status list | IA 3.5.3 |
| 6.2 | Conditional Access policies | Azure AD → Security → Conditional Access → Policies. Review all policies. | Policies enforce MFA for all cloud apps. Device compliance required for access. Session controls configured. | Screenshot of CA policy list | AC 3.1.12, AC 3.1.18, IA 3.5.3 |
| 6.3 | External sharing settings | SharePoint Admin → Policies → Sharing. Review external sharing for all sites. | External sharing restricted to specific domains or disabled entirely. No "Anyone" links. | Screenshot of sharing settings | AC 3.1.3, SC 3.13.19 |
| 6.4 | Guest user access review | Azure AD → Users → External Users. Review guest accounts. | Guest accounts are limited, reviewed, and justified. No stale/inactive guest accounts. | Screenshot of guest user list | AC 3.1.1 |
| 6.5 | Audit logging | Security & Compliance → Audit. Verify audit log is enabled. | Audit logging is ON. Log retention is configured. | Screenshot of audit config | AU 3.3.1 |
| 6.6 | DLP policies | Security & Compliance → Data Loss Prevention. Review DLP policies. | DLP policies exist for sensitive data types (PII, CUI). | Screenshot of DLP policies | AC 3.1.3 |
| 6.7 | Password policy (cloud) | Azure AD → Security → Authentication methods → Password protection. Review settings. | Password protection enabled. Custom banned passwords list configured. | Screenshot | IA 3.5.7 |
| 6.8 | Admin role assignments | Azure AD → Roles and administrators. List privileged role assignments. | Limited number of Global Admins. Privileged roles assigned by Just-In-Time/PIM. | Screenshot of admin roles | AC 3.1.5, AC 3.1.15 |
| 6.9 | Modern authentication status | M365 Admin → Settings → Org settings → Modern authentication. | Modern authentication is enabled. Basic auth for legacy protocols is disabled. | Screenshot | IA 3.5.4 |
| 6.10 | Security defaults or Identity Protection | Azure AD → Properties → Security defaults (or Identity Protection). | Security defaults enabled OR equivalent Conditional Access policies configured. | Screenshot | IA 3.5.3 |

---

### 7. Cloud Tenant Verification — Property Management SaaS

**Target:** Property Management SaaS (CLOUD-PMS)
**Access Required:** Admin account in PM SaaS

| # | Verification Item | Procedure | Expected Result | Evidence | Controls |
|:-:|-------------------|-----------|-----------------|----------|:--------:|
| 7.1 | MFA availability and enforcement | Review user settings. Check if MFA is available and enforced. | MFA is supported and enforced (or available). | Screenshot of security settings | IA 3.5.3 |
| 7.2 | User role permissions | List users and their roles/permissions. Review role definitions. | Roles follow least privilege. No users have excess permissions. | Screenshot of user roles | AC 3.1.2, AC 3.1.5 |
| 7.3 | Data encryption (in transit) | Check if HTTPS is enforced (browser check for TLS). | HTTPS required. TLS 1.2 or higher. | Screenshot of browser connection | SC 3.13.8 |
| 7.4 | Data encryption (at rest) | Review vendor documentation or SOC 2 report. | Vendor confirms encryption at rest. | Vendor docs or SOC 2 excerpt | SC 3.13.14 |
| 7.5 | Session timeout | Check session timeout settings. | Session expires after inactivity. | Screenshot of timeout config | AC 3.1.11 |
| 7.6 | Audit logging / activity log | Review activity log availability. | User activity is logged and available for review. | Screenshot of activity log | AU 3.3.1 |
| 7.7 | External data sharing settings | Review data export/sharing settings. | Controls on data export prevent unauthorized data exfiltration. | Screenshot | AC 3.1.3 |

---

### 8. Mobile Device Verification

**Target:** Sample of company mobile devices (MOB-001 to MOB-005) and BYOD policy review
**Access Required:** Device access or MDM console

| # | Verification Item | Procedure | Expected Result | Evidence | Controls |
|:-:|-------------------|-----------|-----------------|----------|:--------:|
| 8.1 | Company mobile device encryption | Check device settings → Security → Encryption. | Device encryption enabled. | Screenshot of encryption status | AC 3.1.19, SC 3.13.14 |
| 8.2 | Company mobile device passcode | Check passcode/PIN requirements. | Strong passcode or biometric authentication required. | Screenshot | AC 3.1.18 |
| 8.3 | MDM enrollment | Check if device is enrolled in MDM. | Company devices enrolled in MDM with compliance policies applied. | Screenshot of MDM console | AC 3.1.18 |
| 8.4 | MAM / Conditional Access for BYOD | Review MAM policies in M365. | MAM policies apply to BYOD: prevent save-as, require PIN, restrict copy/paste for org data. | Screenshot of MAM policies | AC 3.1.18, SC 3.13.19 |
| 8.5 | Remote wipe capability | Check if remote wipe is configured. | Remote wipe capability is configured for company devices. | Screenshot | MP 3.8.5 |

---

### 9. Physical Security Verification (Observation)

**Target:** Head Office, Property Office A
**Access Required:** Site access

| # | Verification Item | Procedure | Expected Result | Evidence | Controls |
|:-:|-------------------|-----------|-----------------|----------|:--------:|
| 9.1 | Server room physical access | Observe server room door. Is it locked? What type of lock? Who has access? | Locked. Access restricted to authorized personnel. | Photograph | PE 3.10.1 |
| 9.2 | Visitor management | Observe visitor check-in process. Review visitor log. | Visitors sign in, are escorted, and log is maintained. | Photograph of log | PE 3.10.3 |
| 9.3 | Screen locking behavior | Walk through office area. Observe unattended workstations. | Unattended workstations are locked. No visible sensitive data on screens. | Observation note | AC 3.1.10 |
| 9.4 | Clean desk policy | Observe desk areas for sensitive documents. | No CUI/PII documents left on desks or printers. | Photograph | MP 3.8.1 |
| 9.5 | Printer locations | Observe printer locations and document handling. | Printers in secure areas. Printed documents not left unattended. | Observation note | SC 3.13.15 |
| 9.6 | Physical access to property office | Observe property office access. | Office is locked or reception-controlled. | Photograph | PE 3.10.2 |

---

### 10. Log Analysis

**Target:** Sample logs from firewall, NAS, M365
**Access Required:** Read access to logging systems

| # | Verification Item | Procedure | Expected Result | Evidence | Controls |
|:-:|-------------------|-----------|-----------------|----------|:--------:|
| 10.1 | Firewall log review | Export 7 days of firewall logs. Review for blocked inbound attempts, outbound anomalies. | Logs capture source IP, destination, port, action, timestamp. | Log extract (anonymized) | AU 3.3.1 |
| 10.2 | M365 audit log review | Search M365 audit log for user activity in last 7 days. | Audit log contains user activity: logins, file access, admin actions. | Screenshot of audit log | AU 3.3.1, AU 3.3.2 |
| 10.3 | Log review evidence | Request evidence of recent log review (email, report, sign-off). | Log review is performed on scheduled basis. | Document or email | AU 3.3.3 |

---

### 11. Evidence Capture Standards

Each piece of technical evidence must include:

| Field | Requirement |
|-------|-------------|
| **Timestamp** | Date and time evidence was captured |
| **System Name** | Asset ID from inventory (e.g., HQ-WKS-001) |
| **Assessor** | Name of person who captured evidence |
| **Description** | What the evidence shows |
| **File Name** | Evidence file naming convention: `{Control}_{System}_{Item}_{Date}` (e.g., `IA-3.5.3_HQ-WKS-001_MFA-Status_2026-07-20`) |
| **Storage Location** | Evidence stored in `14-Technical-Verification/Evidence/` |
| **Reliability** | High / Medium / Low |

---

### 12. Technical Verification Schedule

| Day | Focus | Systems |
|:---:|-------|---------|
| **Day 1** | Network infrastructure | Firewall, Switch, Wi-Fi |
| **Day 2** | Server + Endpoints (batch 1) | NAS, 4 workstations |
| **Day 3** | Cloud + Endpoints (batch 2) | M365, PM SaaS, 4 workstations |
| **Day 4** | Mobile + Physical | Mobile devices, site observation |
| **Day 5** | Log analysis + follow-up | All systems — fill gaps |

---

### 13. Verification Results Template

Use this template to document each verification item:

```
─────────────────────────────────────────────────────────────
ITEM: 5.3  |  Full Disk Encryption Check
─────────────────────────────────────────────────────────────
System:       HQ-WKS-003 (IT Admin Workstation)
Date:         2026-07-22
Assessor:     Confidential
Result:       PASS
Evidence:     HQ-WKS-003_BitLocker-Status_2026-07-22.png
Notes:        BitLocker enabled, protection ON. Recovery key
              backed up to AD. TPM + PIN configured.
─────────────────────────────────────────────────────────────
```

---

*Document Version: 1.0*
*Date: July 13, 2026*
