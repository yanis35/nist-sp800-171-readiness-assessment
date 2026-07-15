# Gap Analysis & Remediation Plan

## Confidential — NIST SP 800-171 Readiness Assessment

---

### 1. Purpose

This document analyzes the gaps between the organization's current security posture and NIST SP 800-171 compliance, and provides a prioritized remediation plan with resource estimates, owners, and target dates.

This document serves as the organization's **Plan of Actions and Milestones (POA&M)** — the formal record of identified deficiencies and planned remediation required under NIST SP 800-171 3.12.2.

---

### 2. Compliance Gap Summary

| Metric | Value |
|--------|:-----:|
| Total applicable controls | 107 |
| Implemented (I) | 57 |
| Compliance Score (I-only) | **53%** |
| Compliance Score (I + PI) | 75% |
| Findings (PI + NI) | 35 |
| Documented in this plan | 20 (consolidated) |

#### Visual Gap Analysis

```
Implementation Status by Family (Percentage)
─────────────────────────────────────────────────────────────────
AC  ███████████████████████████░░░░░░░░░░░  24% (I=5, PI=10, NI=6)
AT  ████████████░░░░░░░░░░░░░░░░░░░░░░░░░  0%  (I=0, PI=1, NI=2)
AU  ████████████████████████████████░░░░░░  33% (I=3, PI=2, NI=4)
CM  ████████████░░░░░░░░░░░░░░░░░░░░░░░░░  0%  (I=0, PI=4, NI=5)
IA  ██████████████████████████████████████  67% (I=6, PI=3, NI=0)
IR  ████████████░░░░░░░░░░░░░░░░░░░░░░░░░  0%  (I=0, PI=0, NI=3)
MA  ██████████████████████████░░░░░░░░░░░░  0%  (I=0, PI=2, NI=2)*
MP  ██████████████████░░░░░░░░░░░░░░░░░░░░  14% (I=1, PI=3, NI=3)
PS  ██████████████████████████████████████  0%  (I=0, PI=2, NI=0)*
PE  ██████████████████████████████████████  67% (I=4, PI=1, NI=1)
RA  ████████████░░░░░░░░░░░░░░░░░░░░░░░░░  0%  (I=0, PI=1, NI=2)
CA  ████████████░░░░░░░░░░░░░░░░░░░░░░░░░  0%  (I=0, PI=1, NI=5)
SC  ██████████████████████████████████████  53% (I=9, PI=5, NI=3)
SI  ██████████████████████████████████████  43% (I=3, PI=4, NI=0)

* Families with only PI and no I — no control fully implemented
```

---

### 3. Remediation Priority Matrix

```
                     EFFORT TO FIX
                Low              Medium            High
              ┌────────────────────────────────────────────────┐
              │                                                │
    Critical  │ FINDING-003 (MFA)           FINDING-004 (NAS)  │
              │ FINDING-005 (Log Review)    FINDING-008 (DLP)  │
              │ FINDING-006 (BYOD/MDM)                         │
Priority      │ FINDING-007 (Vuln Scan)                        │
              │ FINDING-009 (Change Mgmt)                      │
              ├────────────────────────────────────────────────┤
              │                                                │
    High      │ FINDING-011 (Admin Accts)   FINDING-001 (SSP)  │
              │ FINDING-014 (Logon Banner)  FINDING-002 (IRP)  │
              │ FINDING-019 (Inactive Accts) FINDING-010 (POA&M)│
              │ FINDING-020 (Remote Phys)                      │
              ├────────────────────────────────────────────────┤
              │                                                │
    Medium    │ FINDING-016 (Insider Trng)  FINDING-012 (Split)│
              │ FINDING-017 (Role Trng)     FINDING-013 (Basel)│
              │ FINDING-018 (Trng Compl)    FINDING-015 (Media)│
              └────────────────────────────────────────────────┘

    RECOMMENDED ACTION:
    ┌─────────────────┬──────────────────────────────────────────┐
    │ Quick Wins      │ Do these first — low effort, high impact │
    │ Major Projects  │ High effort, high impact — plan resources │
    │ Strategic       │ Long-term — build into annual planning   │
    └─────────────────┴──────────────────────────────────────────┘
```

---

### 4. Detailed Remediation Plan

#### 4.1 Critical Priority — 30 Days

| ID | Finding | Remediation Steps | Owner | Est. Hours | Est. Cost* | Target Date | Dependencies | Status |
|:--:|---------|-------------------|:-----:|:----------:|:----------:|:-----------:|:------------:|:------:|
| FINDING-003 | MFA Not Fully Deployed | 1. Enable MFA on VPN gateway 2. Enable MFA in PM SaaS 3. Require MFA for MSP connections 4. Test all MFA enforcement 5. Document policy update | IT Manager | 16 | Minimal (licenses exist) | 30 days | Vendor support for VPN MFA | Open |
| FINDING-005 | No Log Review Process | 1. Define log review schedule (daily/weekly) 2. Assign responsibility 3. Create log review checklist 4. Configure logging failure alerts 5. Document process | IT Manager | 8 | Minimal | 30 days | N/A | Open |
| FINDING-006 | BYOD/MDM Not Implemented | 1. Deploy Microsoft Intune (included in BP) 2. Enroll company devices 3. Configure MAM policies for BYOD 4. Configure Conditional Access for device compliance 5. Update BYOD policy | IT Manager | 24 | Included in M365 BP | 30 days | N/A | Open |
| FINDING-007 | No Vulnerability Scanning | 1. Deploy scanning tool (Nessus, Qualys, or M365 Defender) 2. Configure monthly scanning 3. Establish remediation SLAs 4. Run initial scan 5. Remediate findings | IT Manager | 16 | $500-2,000/year (small-scale) | 30 days | Tool procurement | Open |
| FINDING-009 | No Change Management | 1. Develop change management policy (scaled for org size) 2. Create change request template 3. Define approval workflow 4. Communicate to staff and MSP | IT Manager + Exec | 8 | Minimal | 30 days | N/A | Open |

**Quick Wins (30-day total):** $500-2,000, ~72 hours

---

#### 4.2 High Priority — 90 Days

| ID | Finding | Remediation Steps | Owner | Est. Hours | Est. Cost* | Target Date | Dependencies | Status |
|:--:|---------|-------------------|:-----:|:----------:|:----------:|:-----------:|:------------:|:------:|
| FINDING-001 | No System Security Plan | 1. Use assessment outputs (scope, boundary, inventory, data flow, control matrix) as SSP inputs 2. Draft SSP using NIST template 3. Review with Exec 4. Approve and sign 5. Review/update annually | IT Manager + Lead Consultant | 40 | $3,000-5,000 (consultant support) | 90 days | Control Assessment (this assessment) | Open |
| FINDING-002 | No Incident Response Plan | 1. Draft IR Plan using CISA or NIST template 2. Include DFARS 72-hour reporting procedure 3. Define roles and contact lists 4. Schedule tabletop exercise 5. Train staff on reporting | IT Manager | 24 | Minimal (templates free) | 60 days | N/A | Open |
| FINDING-004 | NAS Encryption at Rest | 1. Verify NAS supports encryption 2. Enable volume encryption 3. Securely back up encryption keys 4. Verify encryption is active 5. Document in maintenance records | IT Manager | 4 | Minimal (feature exists) | 30 days | N/A | Open |
| FINDING-008 | No Data Classification / CUI Marking | 1. Develop data classification policy 2. Deploy M365 sensitivity labels 3. Train employees on classification 4. Request CUI designation from prime contractor 5. Implement CUI marking on documents | IT Manager + Exec | 24 | Included in M365 BP | 90 days | CUI designation from prime | Open |
| FINDING-010 | No POA&M or Continuous Monitoring | 1. Create POA&M from this assessment's findings 2. Assign owners and target dates 3. Define monitoring metrics 4. Implement monthly POA&M review 5. Schedule follow-up assessment | IT Manager + Exec | 8 | Minimal | 60 days | Finding register (this document) | Open |

**Major Projects (30-90 day total):** $3,000-5,000, ~100 hours

---

#### 4.3 Medium Priority — 180 Days

| ID | Finding | Remediation Steps | Owner | Est. Hours | Est. Cost* | Target Date | Dependencies | Status |
|:--:|---------|-------------------|:-----:|:----------:|:----------:|:-----------:|:------------:|:------:|
| FINDING-011 | IT Single Privileged Account | 1. Create separate admin accounts for IT staff 2. Remove admin rights from user accounts 3. Configure PIM (Azure AD) for JIT access 4. Train IT on account separation | IT Manager | 4 | Minimal | 30 days | N/A | Open |
| FINDING-012 | VPN Split-Tunneling | 1. Test full-tunnel VPN on pilot user 2. Assess performance impact 3. Reconfigure to full-tunnel 4. Deploy to all remote users 5. Verify no direct-to-internet traffic while VPN connected | IT Manager | 8 | Minimal | 60 days | FINDING-003 (MFA on VPN) | Open |
| FINDING-013 | No Configuration Baselines | 1. Select CIS Benchmarks as standard 2. Apply baseline to one system type first 3. Deploy via GPO where possible 4. Document baseline configurations 5. Schedule quarterly review | IT Manager | 40 | Minimal (CIS free) | 180 days | N/A | Open |
| FINDING-014 | No Logon Banner | 1. Configure interactive logon message via GPO 2. Use approved legal text 3. Deploy to all workstations 4. Verify on sample | IT Manager | 2 | Minimal | 30 days | N/A | Open |
| FINDING-015 | Media Sanitization Missing | 1. Develop sanitization policy (NIST SP 800-88) 2. Secure existing decommissioned drives 3. Procure shredding/destruction service 4. Sanitize or destroy existing drives 5. Document with certificates | IT Manager | 8 | $500-1,000 (shredding service) | 90 days | N/A | Open |
| FINDING-016 | No Insider Threat Training | 1. Incorporate insider threat awareness into annual training 2. Define indicators and reporting channels 3. Deliver training 4. Test comprehension | IT Manager + Admin | 4 | Minimal | 180 days | FINDING-017 (role-based training) | Open |
| FINDING-017 | No Role-Based Training | 1. Develop role-specific content: CUI handlers, IT, general 2. Deliver to all personnel 3. Document completion 4. Schedule annual refresher | IT Manager + Admin | 16 | Minimal | 180 days | N/A | Open |

**Medium-term (30-180 day total):** $500-1,000, ~82 hours

---

#### 4.4 Low Priority — 365 Days

| ID | Finding | Remediation Steps | Owner | Est. Hours | Est. Cost* | Target Date | Dependencies | Status |
|:--:|---------|-------------------|:-----:|:----------:|:----------:|:-----------:|:------------:|:------:|
| FINDING-018 | Training Completion Not Enforced | 1. Implement training completion tracking 2. Report to Exec monthly 3. Enforce access suspension for non-completion 4. Automate reminders | IT Manager | 4 | Minimal | 90 days | FINDING-017 | Open |
| FINDING-019 | Inactive Accounts Not Audited | 1. Disable identified inactive accounts immediately 2. Implement quarterly account review 3. Configure Azure AD inactive account detection | IT Manager | 4 | Minimal | 30 days | N/A | Open |
| FINDING-020 | No Remote Work Physical Security | 1. Update remote work policy to include physical security 2. Include in annual training 3. Verify compliance via annual attestation | Admin | 4 | Minimal | 180 days | N/A | Open |

**Ongoing (30-365 day total):** Minimal, ~12 hours

---

### 5. Remediation Cost Summary

| Priority | Total Hours | Estimated Direct Cost | Timeline |
|----------|:-----------:|:---------------------:|:--------:|
| **Critical** | 72 | $500 - $2,000 | 30 days |
| **High** | 100 | $3,000 - $5,000 | 90 days |
| **Medium** | 82 | $500 - $1,000 | 180 days |
| **Low** | 12 | Minimal | 365 days |
| **TOTAL** | **266 hours** | **$4,000 - $8,000** | **12 months** |

**Staffing Assumption:** Most remediation performed by IT Manager (existing staff). Consultant support recommended for SSP development. No additional FTE required.

**Cost Note:** Costs are estimated for a 20-person organization using existing licensing (M365 Business Premium) where possible. Additional tooling costs (vulnerability scanning, media destruction) are minor.

---

### 6. Risk Acceptance

The following findings could be considered for **risk acceptance** if resources are constrained. Acceptance requires Executive approval and documentation of the rationale.

| Finding | Acceptable? | Rationale for Acceptance |
|:-------:|:-----------:|--------------------------|
| FINDING-012 (Split-Tunnel) | **Conditional** | Acceptable only if compensating controls (endpoint firewall, EDR, user training) are in place. Risk of bypassing org firewall is understood. |
| FINDING-014 (Logon Banner) | **Yes** | Legal risk is low for a 20-person org. Administrative finding. Defer to 90 days. |
| FINDING-015 (Media Sanitization) | **Conditional** | Acceptable only if all decommissioned media is physically secured. Cannot accept if media is in uncontrolled storage. |
| FINDING-018 (Training Completion) | **Conditional** | Acceptable only if 90%+ completion is achieved. Current 70% is not acceptable. |
| FINDING-020 (Remote Work Physical) | **Yes** | Low risk for current environment. Defer to annual policy update. |

---

### 7. Compliance Roadmap — 12 Months

```
MONTH 1  | 30-DAY SPRINT — Critical Findings
         │ ████████████████████████████████████
         │ MFA deployment (VPN, PM SaaS, MSP)
         │ Log review process established
         │ MDM/MAM deployed for mobile devices
         │ Vulnerability scanner deployed
         │ Change management policy created
         │ NAS encryption enabled
         │ Logon banner deployed
         │ Inactive accounts cleaned

MONTH 2  | 30-60 DAY — High Priority Quick Wins
         │ ████████████████████████████████████
         │ Incident Response Plan drafted
         │ POA&M created from this assessment
         │ VPN full-tunnel tested and deployed
         │ IT admin account separation completed

MONTH 3  | 90-DAY MILESTONE — High Priority Projects
         │ ████████████████████████████████████
         │ System Security Plan drafted and reviewed
         │ Data classification policy implemented
         │ CUI sensitivity labels deployed
         │ CUI designation clarified with prime

MONTH 4-6 │ 180-DAY — Medium Priority
         │ ████████████████████████████████████
         │ Configuration baselines (CIS) applied
         │ Media sanitization policy and execution
         │ Role-based training deployed
         │ Insider threat training added
         │ Remote work physical security policy

MONTH 7-9 │ 180-270 DAY — Sustainment
         │ ████████████████████████████████████
         │ SSP finalized and approved
         │ IR tabletop exercise conducted
         │ Vulnerability scanning — second cycle
         │ POA&M review and update

MONTH 10-12 │ 365-DAY — Continuous Improvement
         │ ████████████████████████████████████
         │ Annual security awareness training
         │ Annual control assessment (follow-up)
         │ POA&M close-out review
         │ Prepare for formal assessment / CMMC
```

---

### 8. Phase 1 Remediation (Quick Wins — First 30 Days)

| Week | Focus | Actions |
|:----:|-------|---------|
| **Week 1** | Foundation | Enable NAS encryption. Create change management process. Configure logon banner. Disable inactive accounts. |
| **Week 2** | Access Controls | Enable MFA on VPN. Request PM SaaS MFA enablement. Require MSP MFA. Separate IT admin accounts. |
| **Week 3** | Monitoring | Deploy vulnerability scanner (first scan). Create log review checklist. Start daily log review. |
| **Week 4** | Mobile + Process | Deploy Intune/MAM. Enroll company devices. Configure Conditional Access for mobile. Document log review process. |

---

### 9. Remediation Responsibilities

| Role | Responsibilities |
|------|-----------------|
| **IT Manager** | Primary implementer of all technical remediation items |
| **Managed Service Provider (MSP)** | Support IT Manager with network-level changes (VPN, firewall) |
| **Executive Sponsor** | Approve policy changes, allocate budget, sign SSP, accept risk decisions |
| **Admin / HR** | Support training development, policy communication, account management process |
| **Lead Consultant (External)** | SSP development support, IR Plan review, technical guidance as needed |

---

### 10. Verification of Remediation

Each remediated finding should be verified before closure:

| Verification Method | When | Example |
|--------------------|:----:|---------|
| **Technical verification** | After implementation | Verify MFA is enforced by attempting access |
| **Document review** | After policy creation | Verify policy meets NIST requirements |
| **Interview** | After training | Verify employees recall training content |
| **Observation** | After process change | Verify log review is being performed |

**Closure Criteria:** Finding is closed when the control is rated **Implemented (I)** in a follow-up assessment.

---

*Document Version: 1.0*
*Date: July 20, 2026*
