# Evidence Collection Plan

## Confidential — NIST SP 800-171 Readiness Assessment

---

### 1. Purpose

This document defines the specific evidence items required to assess each NIST SP 800-171 control family, identifies the source of each evidence item, assigns collection responsibility, and establishes the collection schedule.

This plan serves as the **Evidence Request List (ERL)** that will be communicated to the organization at the start of evidence collection activities.

---

### 2. Evidence Collection Principles

| Principle | Description |
|-----------|-------------|
| **Sufficiency** | Sufficient evidence must be collected to support each finding. A single source is rarely sufficient. |
| **Corroboration** | Findings must be supported by at least two independent evidence sources where possible. |
| **Timeliness** | Evidence must reflect the current state of controls. Evidence older than 12 months is generally insufficient unless it is a foundational document (e.g., policy). |
| **Reliability** | Evidence from authoritative sources (system configurations, signed policies) is weighted more heavily than anecdotal evidence (verbal claims unsupported by documentation). |
| **Traceability** | Every evidence item must be traceable to the specific requirement(s) it supports via the Evidence Register. |

---

### 3. Evidence Request List by Control Family

#### 3.1 Access Control (AC)

| ID | Evidence Item | Source | Method | Priority | Related Reqs |
|:--:|---------------|--------|--------|:--------:|:------------:|
| EVD-AC-01 | Access Control Policy (signed, dated) | IT Manager | Document Request | High | 3.1.1 – 3.1.22 |
| EVD-AC-02 | User access list (all systems with CUI access) | IT Manager | Document Request | High | 3.1.1, 3.1.2 |
| EVD-AC-03 | Role-based access control matrix | IT Manager | Document Request | Medium | 3.1.2, 3.1.5 |
| EVD-AC-04 | Remote access policy and configuration | IT Manager | Document + Technical | High | 3.1.12 – 3.1.15 |
| EVD-AC-05 | VPN configuration (protocol, cipher, auth method) | IT Manager | Technical | High | 3.1.13, 3.1.14 |
| EVD-AC-06 | Wireless configuration (SSID segmentation, encryption) | IT Manager | Technical | Medium | 3.1.16, 3.1.17 |
| EVD-AC-07 | Mobile device management policy and configuration | IT Manager | Document + Technical | High | 3.1.18, 3.1.19 |
| EVD-AC-08 | BYOD policy / Acceptable Use Policy | IT Manager | Document | High | 3.1.18, 3.1.19 |
| EVD-AC-09 | Session lock / timeout configuration (workstations) | IT Manager | Technical (sample) | Medium | 3.1.10, 3.1.11 |
| EVD-AC-10 | Account lockout policy (GPO or equivalent) | IT Manager | Technical | Medium | 3.1.8 |
| EVD-AC-11 | Logon banner configuration | IT Manager | Technical | Low | 3.1.9 |
| EVD-AC-12 | USB / portable storage restriction configuration | IT Manager | Technical | Medium | 3.1.20 |
| EVD-AC-13 | Administrator vs. user account separation evidence | IT Manager | Technical | High | 3.1.5 – 3.1.7 |

#### 3.2 Awareness & Training (AT)

| ID | Evidence Item | Source | Method | Priority | Related Reqs |
|:--:|---------------|--------|--------|:--------:|:------------:|
| EVD-AT-01 | Security awareness training program/policy | IT Manager | Document | High | 3.2.1 |
| EVD-AT-02 | Training records (attendance, completion) | Admin / HR | Document | High | 3.2.1 |
| EVD-AT-03 | Role-based training materials (CUI handling) | IT Manager | Document | Medium | 3.2.2 |
| EVD-AT-04 | Insider threat awareness training materials | IT Manager | Document | Medium | 3.2.3 |
| EVD-AT-05 | Training schedule / frequency evidence | IT Manager | Document | Low | 3.2.1 |

#### 3.3 Audit & Accountability (AU)

| ID | Evidence Item | Source | Method | Priority | Related Reqs |
|:--:|---------------|--------|--------|:--------:|:------------:|
| EVD-AU-01 | Audit logging policy / configuration | IT Manager | Document | High | 3.3.1 |
| EVD-AU-02 | Audit log configuration (NAS, M365, firewall, endpoints) | IT Manager | Technical | High | 3.3.1, 3.3.2 |
| EVD-AU-03 | Sample audit logs (7 days of logs) | IT Manager | Technical | High | 3.3.1 |
| EVD-AU-04 | Log review procedure / evidence of log review | IT Manager | Document + Interview | High | 3.3.3 |
| EVD-AU-05 | Audit log protection / access restriction configuration | IT Manager | Technical | Medium | 3.3.8, 3.3.9 |
| EVD-AU-06 | NTP / time synchronization configuration | IT Manager | Technical | Medium | 3.3.7 |
| EVD-AU-07 | Log alerting / failure notification configuration | IT Manager | Technical | Medium | 3.3.4 |

#### 3.4 Configuration Management (CM)

| ID | Evidence Item | Source | Method | Priority | Related Reqs |
|:--:|---------------|--------|--------|:--------:|:------------:|
| EVD-CM-01 | System baseline configuration documentation | IT Manager | Document | High | 3.4.1 |
| EVD-CM-02 | Configuration management policy | IT Manager | Document | High | 3.4.1 |
| EVD-CM-03 | Security hardening standards (CIS benchmarks, STIGs) | IT Manager | Document | High | 3.4.2 |
| EVD-CM-04 | Sample workstation configuration (security settings) | IT Manager | Technical (sample) | High | 3.4.2 |
| EVD-CM-05 | Change management policy / procedure | IT Manager | Document | High | 3.4.3, 3.4.4 |
| EVD-CM-06 | Recent change request / approval records | IT Manager | Document | Medium | 3.4.3 |
| EVD-CM-07 | Software restriction / whitelisting configuration | IT Manager | Technical | Medium | 3.4.7, 3.4.8 |
| EVD-CM-08 | Inventory of authorized software | IT Manager | Document | Medium | 3.4.1 |

#### 3.5 Identification & Authentication (IA)

| ID | Evidence Item | Source | Method | Priority | Related Reqs |
|:--:|---------------|--------|--------|:--------:|:------------:|
| EVD-IA-01 | Identity and authentication policy | IT Manager | Document | High | 3.5.1 – 3.5.9 |
| EVD-IA-02 | MFA configuration (M365, VPN, PM SaaS) | IT Manager | Technical | **Critical** | 3.5.3 |
| EVD-IA-03 | Password policy configuration (length, complexity, history) | IT Manager | Technical | High | 3.5.7, 3.5.8 |
| EVD-IA-04 | User account list (active, disabled, terminated) | IT Manager | Technical | High | 3.5.1, 3.5.6 |
| EVD-IA-05 | Service account management policy / list | IT Manager | Document | Medium | 3.5.1 |
| EVD-IA-06 | Temporary account / password procedure | IT Manager | Document | Low | 3.5.9 |
| EVD-IA-07 | Replay-resistant authentication evidence (Kerberos, modern auth) | IT Manager | Technical | Medium | 3.5.4 |

#### 3.6 Incident Response (IR)

| ID | Evidence Item | Source | Method | Priority | Related Reqs |
|:--:|---------------|--------|--------|:--------:|:------------:|
| EVD-IR-01 | Incident Response Plan (signed, dated) | IT Manager / Exec | Document | **Critical** | 3.6.1 |
| EVD-IR-02 | Incident response procedure / playbooks | IT Manager | Document | High | 3.6.1 |
| EVD-IR-03 | Incident reporting process (internal and to DoD) | IT Manager | Document + Interview | High | 3.6.2 |
| EVD-IR-04 | Incident response test / tabletop exercise records | IT Manager | Document | High | 3.6.3 |
| EVD-IR-05 | Incident history / past incident records | IT Manager | Document | Medium | 3.6.1 |

#### 3.7 Maintenance (MA)

| ID | Evidence Item | Source | Method | Priority | Related Reqs |
|:--:|---------------|--------|--------|:--------:|:------------:|
| EVD-MA-01 | System maintenance / patch management policy | IT Manager | Document | High | 3.7.1 |
| EVD-MA-02 | Patch management records (last 6 months) | IT Manager | Document | High | 3.7.1 |
| EVD-MA-03 | MSP maintenance agreement / SLA (security controls) | IT Manager | Document | High | 3.7.2 |
| EVD-MA-04 | MFA evidence for MSP remote maintenance access | IT Manager | Technical + Interview | High | 3.7.5 |
| EVD-MA-05 | Maintenance log / supervision records | IT Manager | Document | Medium | 3.7.6 |

#### 3.8 Media Protection (MP)

| ID | Evidence Item | Source | Method | Priority | Related Reqs |
|:--:|---------------|--------|--------|:--------:|:------------:|
| EVD-MP-01 | Media protection policy | IT Manager | Document | High | 3.8.1 – 3.8.9 |
| EVD-MP-02 | Removable media usage policy / procedure | IT Manager | Document | High | 3.8.3, 3.8.4 |
| EVD-MP-03 | Backup encryption configuration | IT Manager | Technical | High | 3.8.9 |
| EVD-MP-04 | Media sanitization / disposal procedure | IT Manager | Document | Medium | 3.8.5 |
| EVD-MP-05 | Data at rest encryption configuration (NAS, laptops) | IT Manager | Technical | High | 3.8.1 |

#### 3.9 Personnel Security (PS)

| ID | Evidence Item | Source | Method | Priority | Related Reqs |
|:--:|---------------|--------|--------|:--------:|:------------:|
| EVD-PS-01 | Personnel screening / background check policy | Admin / HR | Document | High | 3.9.1 |
| EVD-PS-02 | Background check records (sample of current employees) | Admin / HR | Document | High | 3.9.1 |
| EVD-PS-03 | Termination / transfer checklist and account deactivation procedure | IT Manager | Document + Interview | High | 3.9.2 |
| EVD-PS-04 | Recent termination handling evidence (if applicable) | IT Manager | Document | Medium | 3.9.2 |

#### 3.10 Physical Protection (PE)

| ID | Evidence Item | Source | Method | Priority | Related Reqs |
|:--:|---------------|--------|--------|:--------:|:------------:|
| EVD-PE-01 | Physical security policy | IT Manager | Document | High | 3.10.1, 3.10.2 |
| EVD-PE-02 | Server room physical access controls (observation) | Lead Consultant | Observation | High | 3.10.1 |
| EVD-PE-03 | Visitor log / visitor management procedure | Admin | Document + Observation | Medium | 3.10.3 |
| EVD-PE-04 | Physical access audit logs (if electronic) | IT / Admin | Document | Medium | 3.10.4 |
| EVD-PE-05 | Remote worker physical security policy | IT Manager | Document | Medium | 3.10.6 |
| EVD-PE-06 | Property office physical security (observation) | Lead Consultant | Observation | Medium | 3.10.1, 3.10.2 |

#### 3.11 Risk Assessment (RA)

| ID | Evidence Item | Source | Method | Priority | Related Reqs |
|:--:|---------------|--------|--------|:--------:|:------------:|
| EVD-RA-01 | Risk assessment policy / procedure | IT Manager / Exec | Document | High | 3.11.1 |
| EVD-RA-02 | Previous risk assessment reports (if any) | IT Manager | Document | High | 3.11.1 |
| EVD-RA-03 | Vulnerability scan results (recent) | IT Manager | Technical | High | 3.11.2 |
| EVD-RA-04 | Vulnerability remediation / patch management records | IT Manager | Document | High | 3.11.3 |

#### 3.12 Security Assessment (CA)

| ID | Evidence Item | Source | Method | Priority | Related Reqs |
|:--:|---------------|--------|--------|:--------:|:------------:|
| EVD-CA-01 | System Security Plan (SSP) — if exists | IT Manager | Document | **Critical** | 3.12.4 |
| EVD-CA-02 | Plan of Actions and Milestones (POA&M) — if exists | IT Manager | Document | High | 3.12.2 |
| EVD-CA-03 | Continuous monitoring policy / procedure | IT Manager | Document | High | 3.12.1, 3.12.3 |
| EVD-CA-04 | Previous assessment / audit reports | IT Manager | Document | Medium | 3.12.6 |

#### 3.13 System & Communications Protection (SC)

| ID | Evidence Item | Source | Method | Priority | Related Reqs |
|:--:|---------------|--------|--------|:--------:|:------------:|
| EVD-SC-01 | Network architecture diagram (current) | IT Manager | Document | **Critical** | 3.13.1, 3.13.2 |
| EVD-SC-02 | Firewall rule set (configuration export) | IT Manager | Technical | High | 3.13.1, 3.13.6 |
| EVD-SC-03 | Encryption in transit configuration (VPN, M365 TLS, SaaS) | IT Manager | Technical | **Critical** | 3.13.8, 3.13.11 |
| EVD-SC-04 | Encryption at rest configuration (NAS, laptop FDE, cloud) | IT Manager | Technical | **Critical** | 3.13.14 |
| EVD-SC-05 | FIPS 140-2/3 validation evidence for cryptographic modules | IT Manager | Technical | High | 3.13.11 |
| EVD-SC-06 | Network segmentation / VLAN configuration | IT Manager | Technical | High | 3.13.3, 3.13.5 |
| EVD-SC-07 | Guest Wi-Fi isolation evidence | IT Manager | Technical | Medium | 3.13.5 |
| EVD-SC-08 | Cloud security configuration (M365 Defender, Conditional Access) | IT Manager | Technical | High | 3.13.1, 3.13.17 |
| EVD-SC-09 | PM SaaS vendor security documentation (SOC 2, encryption) | IT Manager | Document | High | 3.13.8, 3.13.14 |
| EVD-SC-10 | Split-tunneling policy / VPN configuration | IT Manager | Technical | Medium | 3.13.7 |
| EVD-SC-11 | Session termination / timeout configuration (VPN, cloud) | IT Manager | Technical | Medium | 3.13.9 |

#### 3.14 System & Information Integrity (SI)

| ID | Evidence Item | Source | Method | Priority | Related Reqs |
|:--:|---------------|--------|--------|:--------:|:------------:|
| EVD-SI-01 | Malware protection policy / procedure | IT Manager | Document | High | 3.14.2 |
| EVD-SI-02 | Antivirus / EDR configuration and console export | IT Manager | Technical | High | 3.14.2, 3.14.4 |
| EVD-SI-03 | Patch management policy / recent patch records | IT Manager | Document + Technical | High | 3.14.1 |
| EVD-SI-04 | Vulnerability scan results (recent) | IT Manager | Technical | High | 3.14.5 |
| EVD-SI-05 | System monitoring / alerting evidence | IT Manager | Technical | Medium | 3.14.6 |
| EVD-SI-06 | Security alert / advisory subscription evidence | IT Manager | Interview | Medium | 3.14.3 |

---

### 4. Collection Schedule

| Week | Activities | Evidence Collection Focus |
|:----:|------------|--------------------------|
| **Week 1** | Kickoff, initial document request | ERL sent to organization; foundational documents requested (policies, plans) |
| **Week 2** | Document review | Policies, procedures, plans reviewed for all families |
| **Week 3** | Interviews + technical evidence request | Personnel interviews begin; technical evidence requested (configs, logs) |
| **Week 4** | Technical verification | System configuration review, log analysis, sample testing |
| **Week 5** | Gap analysis + follow-up | Missing evidence collected; additional samples if needed |
| **Week 6** | Finalize + report | Evidence register closed; findings substantiated |

---

### 5. Evidence Register Template

| EVD ID | Family | Item Description | Source | Date Req | Date Recv | Status | Location | Related Reqs | Notes |
|:------:|:------:|:----------------:|:------:|:--------:|:---------:|:------:|:--------:|:------------:|:-----:|
| EVD-AC-01 | AC | Access Control Policy | IT Mgr | 2026-07-13 | | Pending | TBD | 3.1.1-22 | |
| EVD-IA-02 | IA | MFA Configuration | IT Mgr | 2026-07-13 | | Pending | TBD | 3.5.3 | Critical |
| ... | ... | ... | ... | ... | ... | ... | ... | ... | ... |

**Status Values:** Pending, Requested, Received, Reviewed, Insufficient, N/A

---

### 6. Responsible Parties

| Role | Evidence Responsibilities |
|------|--------------------------|
| **IT Manager** | Primary evidence provider — policies, system configurations, logs, technical access |
| **Executive Sponsor** | Strategic documents — contract terms, risk acceptance, budget approvals |
| **Admin / HR** | Personnel records — training records, background checks, termination checklists |
| **Property Managers** | Operational evidence — process walkthroughs, data handling demonstrations |
| **Construction Manager** | Operational evidence — project management data access, field practices |
| **Lead Consultant** | Evidence collection, review, verification, and documentation |

---

### 7. Evidence Format Requirements

| Evidence Type | Preferred Format | Notes |
|---------------|------------------|-------|
| Policies / Procedures | PDF (signed) or Word (with approval evidence) | Must include date, version, and approval signature |
| System Configurations | Screenshot or export (PDF, TXT, CSV) | Include timestamp and system identifier |
| Logs | CSV or TXT export (redacted if necessary) | Minimum 7 days of logs |
| Audit Reports | PDF (original) | SOC 2, penetration test, previous assessments |
| Interview Notes | PDF or Word (signed by interviewee) | Structured notes with questions and responses |
| Photographs | JPEG / PNG | Physical security observations only (no personnel photos) |

---

### 8. Evidence Collection Risks and Mitigations

| Risk | Impact | Mitigation |
|------|:------:|------------|
| Client delays evidence submission | High — timeline slippage | Send ERL early; follow up weekly; escalate to Executive Sponsor |
| Evidence is insufficient | Medium — weakened findings | Request additional evidence; use interview to supplement |
| Technical evidence unavailable (e.g., no EDR console) | Medium — limited verification | Document as limitation; rely on alternative evidence |
| Client provides only screenshots (not exports) | Low — harder to verify | Request exports where possible; accept screenshots with timestamp |
| Evidence contains PII/CUI | Medium — handling requirement | Store evidence in encrypted location; mark as confidential; limit access |

---

*Document Version: 1.0*
*Date: July 13, 2026*
