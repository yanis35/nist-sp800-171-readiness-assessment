# Assessment Methodology

## Confidential — NIST SP 800-171 Readiness Assessment

---

### 1. Purpose

This document defines the methodology used to assess the organization's compliance with NIST SP 800-171 Rev 2 security requirements. The methodology ensures consistency, repeatability, and defensibility across all control assessments.

Every finding, gap, and recommendation in the final report traces back to the procedures defined in this document.

---

### 2. Assessment Approach

This assessment employs a **multi-method approach** combining four evidence collection techniques. Each control is assessed using one or more of these methods:

```
┌─────────────────────────────────────────────────────────┐
│                 ASSESSMENT APPROACH                      │
├─────────────┬─────────────┬──────────────┬──────────────┤
│   Document  │  Interview  │  Technical   │ Observation  │
│    Review   │             │   Testing    │              │
├─────────────┼─────────────┼──────────────┼──────────────┤
│ Policies    │ Personnel   │ System       │ Physical     │
│ Procedures  │ discussions │ config       │ walkthrough  │
│ Plans       │ Process     │ Log analysis │ Process demo │
│ Records     │ walkthroughs│ Scan results │ Access       │
│ Contracts   │ Knowledge   │ Network      │ verification │
│             │ assessment  │ review       │              │
├─────────────┼─────────────┼──────────────┼──────────────┤
│ What is     │ What people │ What systems │ What really  │
│ documented  │ say happens │ show happens │ happens      │
└─────────────┴─────────────┴──────────────┴──────────────┘
```

#### 2.1 Document Review

| Element | Description |
|---------|-------------|
| **Purpose** | Verify that required policies, procedures, plans, and records exist and meet NIST SP 800-171 requirements |
| **Evidence Sources** | Information Security Policy, Acceptable Use Policy, Access Control Policy, Incident Response Plan, System Security Plan (if exists), Configuration Standards, Training Records, Patch Management Records, Previous Assessment Reports |
| **Success Criteria** | Document exists, is approved by appropriate authority, contains required content, is dated within review cycle, and is accessible to affected personnel |

#### 2.2 Interview

| Element | Description |
|---------|-------------|
| **Purpose** | Assess personnel awareness, understanding, and adherence to security policies and procedures |
| **Interview Pool** | Executive Sponsor, IT Manager, IT Support, Property Managers (x2), Construction Manager, Finance Manager, Administrative Staff |
| **Interview Types** | Structured (predefined questions), Semi-structured (follow-up probing), Process walkthrough ("walk me through how you onboard a new tenant") |
| **Success Criteria** | Personnel can articulate their security responsibilities, describe processes accurately, and demonstrate awareness of CUI handling requirements |

#### 2.3 Technical Testing

| Element | Description |
|---------|-------------|
| **Purpose** | Directly verify system configuration and control implementation through technical examination |
| **Methods** | Configuration review, Log analysis, Network architecture review, Access control list review, Encryption verification, MFA configuration review, Patch level verification |
| **Scope** | All in-scope systems defined in the System Boundary document |
| **Success Criteria** | Technical configuration matches documented policy and meets NIST SP 800-171 requirements |

#### 2.4 Observation

| Element | Description |
|---------|-------------|
| **Purpose** | Verify physical security controls and observe actual behavior vs. documented policy |
| **Methods** | Physical walkthrough of head office server room, Observation of workstation security (screen locks, clean desk), Visitor access procedures, Media handling practices |
| **Scope** | Head office, property management offices (sample) |

---

### 3. Evidence Collection by Control Family

| Family | Primary Method | Secondary Method | Tertiary Method |
|--------|:--------------:|:----------------:|:---------------:|
| **AC** — Access Control | Document Review + Technical Testing | Interview | Observation |
| **AT** — Awareness & Training | Document Review | Interview | — |
| **AU** — Audit & Accountability | Technical Testing | Document Review | Interview |
| **CM** — Configuration Management | Technical Testing | Document Review | Interview |
| **IA** — Identification & Authentication | Technical Testing | Document Review | Interview |
| **IR** — Incident Response | Document Review | Interview | Technical Testing |
| **MA** — Maintenance | Document Review | Interview | Technical Testing |
| **MP** — Media Protection | Document Review | Observation | Interview |
| **PS** — Personnel Security | Document Review | Interview | — |
| **PE** — Physical Protection | Observation | Document Review | Interview |
| **RA** — Risk Assessment | Document Review | Interview | Technical Testing |
| **CA** — Security Assessment | Document Review | Interview | Technical Testing |
| **SC** — System & Communications Protection | Technical Testing | Document Review | Interview |
| **SI** — System & Information Integrity | Technical Testing | Document Review | Interview |

---

### 4. Testing Procedures

Each applicable requirement is assessed using the following procedure:

```
Step 1: Understand the Requirement
    ↓ Read the NIST SP 800-171 requirement and discussion
    ↓ Identify the intent and expected outcome
Step 2: Identify Evidence Sources
    ↓ Determine which documents, systems, and personnel hold evidence
Step 3: Collect Evidence
    ↓ Apply primary and secondary methods from Section 3
Step 4: Evaluate Evidence
    ↓ Compare evidence against requirement
    ↓ Apply rating scale (Section 5)
Step 5: Document Finding
    ↓ Record result, evidence references, and rationale
Step 6: Quality Check
    ↓ Verify consistency with other related controls
```

---

### 5. Rating Scale

Each applicable requirement is assigned one of the following ratings:

| Rating | Definition | Evidence Standard | What It Means |
|--------|------------|-------------------|---------------|
| **Implemented (I)** | The control is fully in place and operating as intended. All evidence confirms the requirement is met. | Multiple sources confirm implementation (documentation + technical verification + interview alignment) | No gap. The organization meets this requirement. |
| **Partially Implemented (PI)** | The control exists but has gaps in coverage, documentation, or effectiveness. Some evidence supports implementation, but gaps remain. | At least one source confirms partial implementation, but other sources show gaps or inconsistencies | Gap exists. Remediation is required to achieve full compliance. |
| **Not Implemented (NI)** | The control does not exist or has no evidence of implementation. | No evidence found OR evidence directly contradicts implementation | Significant gap. Remediation is required. |
| **Not Applicable (N/A)** | The control does not apply to the assessed environment. | Documented rationale with supporting justification | No action required. Rationale must be defensible. |

#### 5.1 Rating Guidance

```
                     Evidence Quality
               Low              Medium           High
Needs     ┌────────────┬──────────────────┬──────────────┐
          │            │                  │              │
Critical │     NI      │       NI         │     PI       │
          │            │                  │              │
Importance├────────────┼──────────────────┼──────────────┤
          │            │                  │              │
Moderate │     NI      │       PI         │      I       │
          │            │                  │              │
          ├────────────┼──────────────────┼──────────────┤
          │            │                  │              │
Low      │     PI      │        I         │      I       │
          │            │                  │              │
          └────────────┴──────────────────┴──────────────┘
```

#### 5.2 Use of "Not Applicable"

N/A is assigned **only** when:
- The requirement references a capability the organization does not possess (e.g., no VoIP → 3.13.13 is N/A)
- The requirement references an activity that does not occur (e.g., no media transport → 3.8.6, 3.8.7 are N/A)
- The requirement is inherited from an authorized external provider with documented evidence (e.g., FedRAMP authorization)

**N/A is not used for:**
- Controls that are difficult or expensive to implement (that's a PI or NI finding)
- Controls the organization chose not to implement (that's a gap to remediate)
- Controls the organization "plans to implement later" (that's NI until evidence exists)

---

### 6. Sampling Methodology

For controls that apply to a population of items (e.g., all 20 workstations for encryption testing), sampling is used when full population testing is impractical.

| Population Size | Sample Size | Methodology |
|:---------------:|:-----------:|-------------|
| 2-5 | 100% | Test all items |
| 6-15 | 5-8 | Judgmental sample (include key systems, different locations, different user types) |
| 16-50 | 8-12 | Judgmental sample with diversity criteria |
| 50+ | 10-15 | Statistical or stratified sample |

**This Assessment:**
- 20 workstations → sample of 8 workstations across different locations and user types
- 12 mobile devices → sample of 5 devices (company + BYOD)
- 2 property offices → visit both (100% sample)

#### 6.1 Sample Selection Criteria

Samples are selected to ensure diversity across:

| Criterion | Rationale |
|-----------|-----------|
| **Location** | Head office, property offices, field (different physical security profiles) |
| **User Role** | Executive, IT, Property Management, Construction, Admin (different access profiles) |
| **Device Type** | Desktop, laptop, mobile (different security capabilities) |
| **Ownership** | Company-managed vs. BYOD (different control levels) |
| **CUI Access** | CUI-handling vs. PII-only vs. operational (different risk profiles) |

---

### 7. Evidence Documentation Standards

Each piece of evidence collected during the assessment is documented with:

| Field | Description |
|-------|-------------|
| **Evidence ID** | Unique identifier (e.g., EVD-001) |
| **Source** | Document name, system name, or personnel name |
| **Type** | Document, Interview, Technical, Observation |
| **Date Collected** | Date of evidence collection |
| **Collected By** | Assessor name |
| **Relevant Controls** | Which requirements this evidence supports |
| **Summary** | Brief description of what the evidence shows |
| **Location** | File path or reference location |
| **Reliability** | High / Medium / Low (based on source trustworthiness) |

---

### 8. Assessment Limitations

| Limitation | Implication |
|------------|-------------|
| **No network scanning performed** | Some network-level controls (segmentation, open ports) cannot be fully verified; assessed through configuration review only |
| **No penetration testing** | Control effectiveness is assessed through configuration review, not active exploitation; residual risk may exist |
| **Limited BYOD visibility** | BYOD devices are not managed; assessment relies on policy review and user interviews rather than technical verification |
| **Remote assessment for property offices** | Physical observation at property offices may be limited to scheduled visits; unscheduled observations not possible |
| **MSP cooperation dependent** | MSP technical controls assessed through available documentation and interviews; direct MSP system access may not be available |
| **Cloud provider controls not directly testable** | Cloud provider controls assessed through SOC 2 reports, contracts, and configuration review; direct infrastructure testing not possible |

---

### 9. Methodology Quality Assurance

| Check | Performed By | Timing |
|-------|--------------|--------|
| Peer review of evidence sufficiency | Senior Consultant | Before finalizing each control family |
| Cross-control consistency check | Lead Consultant | After all controls assessed |
| Finding substantiation review | Lead Consultant | During report compilation |
| Methodology deviation log | Lead Consultant | As needed (deviations documented) |

---

### 10. Methodology References

| Reference | Purpose |
|-----------|---------|
| NIST SP 800-171 Rev 2 | Assessment criteria |
| NIST SP 800-53A Rev 5 | Assessment procedures guidance |
| NIST SP 800-115 | Technical testing guide |
| ISO 19011:2018 | Audit management guidelines |
| NIST SP 800-171A | Assessing NIST SP 800-171 requirements |

---

*Document Version: 1.0*
*Date: July 13, 2026*
