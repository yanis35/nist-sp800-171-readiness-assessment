# NIST SP 800-171 Readiness Assessment — Final Report

## Confidential

---

**Engagement Name:** Confidential — NIST SP 800-171 Readiness Assessment

**Assessment Type:** Internal Readiness Assessment (Gap Analysis)

**Framework:** NIST SP 800-171 Rev 2

**Period of Performance:** July 13, 2026 — August 21, 2026

**Date of Report:** August 21, 2026

---

## Document Control

| Version | Date | Author | Description |
|:-------:|:----:|--------|-------------|
| 1.0 | August 21, 2026 | Lead Consultant | Final Report |

---

## Table of Contents

1. Executive Summary
2. Assessment Background
3. Assessment Scope
4. Methodology
5. Assessment Results by Family
6. Strengths
7. Weaknesses and Critical Findings
8. Recommendations
9. Compliance Score Summary
10. Remediation Roadmap
11. Appendices

---

## 1. Executive Summary

### Engagement Overview

A NIST SP 800-171 Rev 2 internal readiness assessment was conducted for a real estate development and property management organization. The assessment evaluated the organization's security posture against 107 applicable security requirements across 14 control families.

### Why This Assessment Was Conducted

The organization is contractually obligated to comply with NIST SP 800-171 as a flow-down requirement from a Department of Defense prime contractor. This readiness assessment serves as the first formal evaluation of compliance posture and provides a baseline for remediation planning.

### Key Findings

| Metric | Result |
|--------|:------:|
| Total applicable controls assessed | 107 |
| Fully implemented | 31 (29%) |
| Partially implemented | 39 (36%) |
| Not implemented | 36 (34%) |
| Not applicable | 6 (6%) |
| Not assessed (insufficient evidence) | 1 (1%) |

### Critical Gaps Identified

1. **No System Security Plan (SSP)** — The organization has not documented how security requirements are implemented for the CUI environment.
2. **No Incident Response Plan** — The organization cannot meet the DFARS 72-hour cyber incident reporting requirement.
3. **Multifactor Authentication Not Fully Deployed** — VPN, Property Management SaaS, and MSP access paths lack MFA.

### Overall Compliance Posture

At **28% implementation**, the organization is in the early stages of NIST SP 800-171 compliance. The weaknesses are concentrated in governance areas (policies, plans, processes) rather than technical controls, which is typical for an organization conducting its first formal assessment. With focused remediation effort over a 12-month period, the organization can achieve a posture suitable for a formal third-party assessment.

---

## 2. Assessment Background

### 2.1 Organization Profile

| Attribute | Detail |
|-----------|--------|
| **Industry** | Real Estate Development & Property Management |
| **Size** | 20 employees |
| **Core Business** | Design, construction, and management of residential housing communities, including military family housing under DoD contract |
| **Compliance Driver** | Prime contractor flow-down requirement under DFARS 252.204-7012 |

### 2.2 Assessment Objective

To assess the organization's current cybersecurity posture against NIST SP 800-171 Rev 2 requirements, identify gaps, and produce a remediation roadmap in advance of a formal third-party assessment or CMMC certification.

### 2.3 Framework

The assessment was conducted against NIST SP 800-171 Rev 2, which defines 113 security requirements across 14 families for protecting Controlled Unclassified Information (CUI) in non-federal systems.

---

## 3. Assessment Scope

### 3.1 In Scope

| Element | Detail |
|---------|--------|
| **Locations** | Head office, property management offices (2), remote worker locations |
| **Systems** | M365 tenant, Property Management SaaS, NAS/File Server, Accounting ERP, Firewall/VPN, company endpoints (20), company mobile devices (5), BYOD mobile devices (~12) |
| **Personnel** | All 20 employees |
| **Data** | Tenant PII, Employee PII, DoD Contract Data, Potential CUI (military housing infrastructure, military tenant PII) |

### 3.2 Out of Scope

| Element | Rationale |
|---------|-----------|
| Construction sites | Temporary locations with no IT infrastructure |
| Construction subcontractors | No system access |
| Physical access control systems | Air-gapped, not connected to IT network |
| Penetration testing | Engagement is a readiness assessment; pentest recommended as future activity |

### 3.3 CUI Determination

Based on available evidence, no formally designated CUI was identified in the environment. However, data exists that could reasonably qualify as CUI (military housing infrastructure details, military tenant PII). A **conservative approach** was applied: all potential CUI is treated as CUI for assessment purposes.

---

## 4. Methodology

### 4.1 Assessment Approach

A multi-method approach was employed:

| Method | Application |
|--------|-------------|
| **Document Review** | Policies, procedures, plans, contracts, training records |
| **Personnel Interviews** | Executive Sponsor, IT Manager, Property Managers, Construction Manager, Finance/Admin, general employees |
| **Technical Verification** | Configuration review, log analysis, network architecture review, endpoint sampling, cloud tenant review |
| **Observation** | Physical security, workstation behavior, clean desk, visitor management |

### 4.2 Rating Scale

| Rating | Definition |
|--------|------------|
| **Implemented (I)** | Control fully in place and operating as intended |
| **Partially Implemented (PI)** | Control exists but has gaps in coverage, documentation, or effectiveness |
| **Not Implemented (NI)** | Control does not exist or no evidence of implementation |
| **Not Applicable (N/A)** | Control does not apply to the assessed environment |

### 4.3 Sampling

Workstations (8 of 20), property offices (2 of 2), mobile devices (5 of ~17), and users (7 of 20) were sampled per the assessment sampling methodology.

---

## 5. Assessment Results by Family

| Family | Implemented | Partial | Not Impl. | N/A | Not Assessed | Score (I only) |
|--------|:-----------:|:-------:|:---------:|:---:|:------------:|:--------------:|
| AC — Access Control | 6 | 11 | 5 | 0 | 0 | 27% |
| AT — Awareness & Training | 0 | 1 | 2 | 0 | 0 | 0% |
| AU — Audit & Accountability | 3 | 3 | 3 | 0 | 0 | 33% |
| CM — Configuration Management | 0 | 5 | 4 | 0 | 0 | 0% |
| IA — Identification & Authentication | 6 | 3 | 0 | 0 | 0 | 67% |
| IR — Incident Response | 0 | 0 | 3 | 0 | 0 | 0% |
| MA — Maintenance | 0 | 2 | 2 | 2 | 0 | 0% |
| MP — Media Protection | 1 | 3 | 3 | 2 | 0 | 14% |
| PS — Personnel Security | 0 | 2 | 0 | 0 | 0 | 0% |
| PE — Physical Protection | 4 | 1 | 1 | 0 | 0 | 67% |
| RA — Risk Assessment | 0 | 1 | 2 | 0 | 0 | 0% |
| CA — Security Assessment | 0 | 1 | 5 | 0 | 0 | 0% |
| SC — System & Communications Protection | 8 | 6 | 3 | 2 | 0 | 47% |
| SI — System & Information Integrity | 3 | 4 | 0 | 0 | 0 | 43% |
| **Total** | **31** | **39** | **36** | **6** | **1** | **29%** |

---

## 6. Strengths

The following areas represent security strengths that should be maintained:

### 6.1 Technical Controls

| Strength | Details |
|----------|---------|
| **Antivirus/EDR** | All company endpoints protected. Real-time protection enabled. Signatures current. |
| **Full Disk Encryption** | All company laptops have BitLocker enabled (verified on sample). |
| **Firewall Configuration** | Default-deny policy. No any/any rules. No exposed RDP/SSH to internet. |
| **Network Segmentation** | Guest Wi-Fi isolated. VLAN segmentation in place. |
| **Account Management** | Unique user accounts with password policy meeting NIST guidance (14-char minimum, complexity, history). |
| **MFA for M365** | MFA enforced for all cloud app access via Conditional Access. |
| **Physical Security** | Server room locked. Access restricted to authorized personnel. |

### 6.2 Operational Practices

| Strength | Details |
|----------|---------|
| **Basic Patching** | Windows updates applied on a recurring (though informal) basis. |
| **Background Screening** | Pre-employment background checks conducted for all staff. |
| **Unique User Accounts** | No shared or generic accounts in use. |

---

## 7. Weaknesses and Critical Findings

### 7.1 Critical Findings

| ID | Finding | Priority |
|:--:|---------|:--------:|
| FINDING-001 | **No System Security Plan (SSP)** — The organization's CUI system operates without an approved SSP. Without it, there is no authoritative documentation of the security boundary, control implementation, or responsible personnel. DFARS compliance requires an SSP. | **Critical** |
| FINDING-002 | **No Incident Response Plan** — The organization cannot demonstrate the ability to respond to a cyber incident involving CUI. The DFARS 72-hour reporting requirement to the DoD is not addressed in any documented procedure. | **Critical** |
| FINDING-003 | **Multifactor Authentication Not Fully Deployed** — While MFA is enforced for M365 cloud access, critical gaps exist: VPN remote access, Property Management SaaS, and MSP maintenance connections do not require MFA. Approximately 40% of access paths to CUI/PII systems lack MFA. | **Critical** |

### 7.2 High Priority Findings

| ID | Finding | Priority |
|:--:|---------|:--------:|
| FINDING-004 | NAS / File Server lacks encryption at rest | High |
| FINDING-005 | No log review process — logs exist but are never examined | High |
| FINDING-006 | BYOD and mobile device management not implemented | High |
| FINDING-007 | No vulnerability scanning program | High |
| FINDING-008 | No data classification or CUI marking procedures | High |
| FINDING-009 | No change management process | High |
| FINDING-010 | No POA&M or continuous monitoring | High |

### 7.3 Systemic Issue

The majority of findings (60%) relate to **governance gaps** — missing policies, plans, and processes — rather than technical control failures. This pattern is characteristic of an organization conducting its first formal compliance assessment. The technical foundation (AV, encryption, patching, firewalls) is functional but lacks the governance framework required for NIST SP 800-171 compliance.

---

## 8. Recommendations

### 8.1 Immediate (30 Days)

| # | Recommendation | Addresses |
|:-:|---------------|:---------:|
| 1 | Enable MFA on VPN gateway, PM SaaS, and MSP connections | FINDING-003 |
| 2 | Implement log review process with defined schedule and responsibility | FINDING-005 |
| 3 | Deploy Microsoft Intune for MDM/MAM; enforce mobile device compliance | FINDING-006 |
| 4 | Deploy vulnerability scanner; perform initial scan | FINDING-007 |
| 5 | Enable NAS volume encryption | FINDING-004 |
| 6 | Create basic change management process | FINDING-009 |
| 7 | Configure logon banner via GPO | FINDING-014 |
| 8 | Separate IT admin and user accounts | FINDING-011 |
| 9 | Disable identified inactive accounts | FINDING-019 |

### 8.2 Short-Term (90 Days)

| # | Recommendation | Addresses |
|:-:|---------------|:---------:|
| 10 | Draft System Security Plan using NIST template | FINDING-001 |
| 11 | Develop Incident Response Plan with DFARS 72-hour reporting | FINDING-002 |
| 12 | Create POA&M from this assessment's findings | FINDING-010 |
| 13 | Implement data classification policy with M365 sensitivity labels | FINDING-008 |
| 14 | Reconfigure VPN to full-tunnel mode | FINDING-012 |
| 15 | Conduct IR tabletop exercise | FINDING-002 |

### 8.3 Medium-Term (180 Days)

| # | Recommendation | Addresses |
|:-:|---------------|:---------:|
| 16 | Apply CIS benchmarks as configuration baselines | FINDING-013 |
| 17 | Develop media sanitization policy; sanitize existing drives | FINDING-015 |
| 18 | Deliver role-based security training for CUI handlers | FINDING-017 |
| 19 | Incorporate insider threat awareness into training | FINDING-016 |
| 20 | Update remote work policy with physical security requirements | FINDING-020 |

### 8.4 Strategic Recommendations

| # | Recommendation | Timeline |
|:-:|---------------|:--------:|
| 21 | Request formal CUI designation from prime contracting officer | 30 days |
| 22 | Engage IT Managed Service Provider with security-specific contract terms | 90 days |
| 23 | Schedule follow-up readiness assessment in 12 months | 365 days |
| 24 | Begin CMMC Level 2 preparation roadmap | 12+ months |

---

## 9. Compliance Score Summary

### 9.1 Overall Score

| Metric | Value |
|--------|:-----:|
| Fully Implemented | 31 of 107 (29%) |
| Partially Implemented | 39 of 107 (36%) |
| Not Implemented | 36 of 107 (34%) |
| Not Applicable | 6 of 107 (6%) |
| Not Assessed | 1 of 107 (1%) |

### 9.2 Score Interpretation

| Score Range | Posture Level | Meaning |
|:-----------:|:-------------:|---------|
| 80-100% | Mature | Ready for formal assessment. Minor gaps only. |
| 60-79% | Developing | Some governance and technical controls in place. Remediation in progress. |
| **40-59%** | **Early Stage** | **Current posture. Foundational controls exist. Governance gaps need addressing.** |
| 0-39% | Initial | Significant gaps. Compliance program needs to be established. |

### 9.3 Score Visualization

```
Overall Compliance Score: 29%
─────────────────────────────────────────────────────────────────
Implemented   ██████████████████████████████████░░░░░░░░░░  29%
Partial       ████████████████████████████████████████░░░░  36%
Not Impl.     ██████████████████████████████████████░░░░░░  34%
N/A           ██████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░   6%
Not Assessed  █░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░   1%

Score by Family (Implemented Only):
─────────────────────────────────────────────────────────────────
AC  ██████████████████████████████████████████░░░░░  27%
AT  ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░   0%
AU  ██████████████████████████████████████░░░░░  33%
CM  ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░   0%
IA  ██████████████████████████████████████████  67%
IR  ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░   0%
MA  ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░   0%*
MP  ██████████████████████████████░░░░░░░░░░░░  14%
PS  ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░   0%*
PE  ██████████████████████████████████████████  67%
RA  ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░   0%
CA  ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░   0%
SC  ████████████████████████████████████████░░░  47%
SI  ███████████████████████████████████████░░░░  43%

* Families where controls exist but none are fully implemented.
```

---

## 10. Remediation Roadmap

### Phase 1: Foundation (Days 1-30)

| Week | Focus Area | Key Actions |
|:----:|------------|-------------|
| 1 | Access Controls | MFA deployment (VPN, PM SaaS, MSP), IT account separation, logon banner |
| 2 | System Hardening | NAS encryption, vulnerability scanner deployment, first scan |
| 3 | Monitoring | Log review process established, inactive account cleanup, logging failure alerts |
| 4 | Mobile Security | Intune/MDM deployment, MAM policies, Conditional Access for mobile |

### Phase 2: Governance (Days 31-90)

| Week | Focus Area | Key Actions |
|:----:|------------|-------------|
| 5-6 | Planning | Draft Incident Response Plan, create POA&M |
| 7-8 | Documentation | Begin System Security Plan, implement data classification |
| 9-10 | Network | VPN full-tunnel reconfiguration, change management process |
| 11-12 | Testing | IR tabletop exercise, vulnerability scan #2 |

### Phase 3: Maturation (Days 91-365)

| Month | Focus Area | Key Actions |
|:-----:|------------|-------------|
| 4-6 | Baselines | CIS benchmarks applied, media sanitization, role-based training |
| 7-9 | Sustainment | SSP finalized, POA&M review, vulnerability scanning quarterly |
| 10-12 | Continuous Improvement | Annual assessment, training refresh, CMMC readiness planning |

### Resource Summary

| Resource | Allocation | Cost Estimate |
|----------|:-----------:|:-------------:|
| IT Manager time | ~266 hours over 12 months | Existing staff |
| MSP support | ~40 hours (network-level changes) | Existing contract |
| Consultant support | ~40 hours (SSP development) | $3,000 - $5,000 |
| Tooling (vulnerability scanning) | Annual license | $500 - $2,000 |
| Media destruction | One-time | $500 - $1,000 |
| **Total Estimated Cost** | | **$4,000 - $8,000** |

---

## 11. Appendices

### Appendix A: System Boundary Diagram

Refer to Phase 5 deliverable: `System-Boundary.md`

### Appendix B: Asset Inventory

Refer to Phase 6 deliverable: `Asset-Inventory.md`

### Appendix C: Data Flow Diagram

Refer to Phase 7 deliverable: `Data-Flow-Diagram.md`

### Appendix D: Control Assessment Matrix (Complete)

Refer to Phase 15 deliverable: `Control-Assessment-Matrix.md`

### Appendix E: Findings Register

Refer to Phase 16 deliverable: `Findings.md`

### Appendix F: Gap Analysis and Remediation Plan

Refer to Phase 17 deliverable: `Gap-Analysis.md`

### Appendix G: Evidence Register

The Evidence Register is maintained in the assessment working papers and is available upon request.

---

## Report Distribution

| Role | Name | Date Distributed |
|------|------|:----------------:|
| Lead Consultant | Confidential | August 21, 2026 |
| Executive Sponsor | Confidential | August 21, 2026 |
| IT Manager | Confidential | August 21, 2026 |

---

*This report contains confidential information intended solely for the named recipient. Distribution outside the organization requires written permission.*

*Assessment conducted in accordance with NIST SP 800-171 Rev 2, NIST SP 800-171A, and NIST SP 800-115 guidelines.*

---

*Document Version: 1.0*
*Date: August 21, 2026*
