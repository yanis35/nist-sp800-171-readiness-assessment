# CUI Identification & Determination

## Confidential — NIST SP 800-171 Readiness Assessment

---

### 1. Purpose

This document identifies whether Controlled Unclassified Information (CUI) exists within the organization's environment, determines which CUI categories may apply, and documents the basis for the determination.

Under DFARS 252.204-7012, the organization is required to safeguard Covered Defense Information (CDI) and CUI. This determination is a prerequisite to scoping the security controls assessed under NIST SP 800-171.

---

### 2. Regulatory Basis

| Source | Requirement |
|--------|-------------|
| **32 CFR Part 2002** | Defines CUI program; establishes CUI Registry |
| **EO 13556** | Establishes CUI program across executive branch |
| **DFARS 252.204-7012** | Requires safeguarding CDI/CUI in contractor systems |
| **CUI Registry (NARA)** | Official list of recognized CUI categories |
| **NIST SP 800-171 Rev 2** | Security requirements for non-federal systems handling CUI |

---

### 3. CUI Registry Review

The following CUI categories from the National Archives CUI Registry were evaluated for applicability to the organization's operations:

| CUI Category | Applicable? | Rationale |
|--------------|:-----------:|-----------|
| **Critical Infrastructure — Infrastructure Vulnerability Information** | **Possible** | Military housing developments may include infrastructure details (utility layouts, structural plans, access points) that could be considered infrastructure vulnerability information if associated with a DoD installation |
| **General Procurement — Procurement and Acquisition** | **Possible** | Contract terms, pricing data, source selection information received from or generated for the DoD prime contractor may qualify |
| **Privacy — Protected Personal Information** | **Possible** | PII of military tenants collected, used, or maintained as part of a government contract may be subject to Privacy Act requirements |
| **Controlled Technical Information (CTI)** | Unlikely | No evidence of technical data with military application (research, engineering, manufacturing) |
| **Export Controlled (ITAR/EAR)** | Unlikely | No defense articles or dual-use technologies in scope of operations |
| **Law Enforcement** | No | No law enforcement functions |
| **Financial — Government** | Unlikely | Not directly handling government financial systems |

---

### 4. Evidence Review

#### 4.1 Contract Document Review

The following evidence was reviewed to identify CUI:

| Evidence Source | CUI Markings Found? | Notes |
|-----------------|:-------------------:|-------|
| DoD Prime Contract (Statement of Work) | **No** | No CUI markings, banner lines, or dissemination controls found |
| Contract Data Requirements List (CDRL) | **No** | No CUI markings |
| Subcontractor flow-down provisions | **Yes — references DFARS clause** | Clause requires compliance, but does not specify CUI categories |
| Correspondence from prime contractor | **No** | No CUI markings in sampled emails |
| Military housing specifications / blueprints | **No markings** | Documents contain sensitive infrastructure details but are not marked as CUI |

#### 4.2 Key Observation

**No documents reviewed to date contain formal CUI markings** (e.g., "CUI" banner, dissemination control markings, or handling instructions as required by 32 CFR Part 2002).

This does **not** definitively mean CUI is absent. It means one of three things:

1. CUI is present but **not marked** by the originating party (a compliance gap by the data originator)
2. The data received does not meet the threshold for CUI classification (most likely scenario for a housing contractor)
3. CUI exists in a form not captured in sampled evidence (e.g., verbal communications, un-reviewed databases)

---

### 5. CUI Determination

#### 5.1 Determination Statement

> **Based on available evidence, the organization does not currently possess formally designated Controlled Unclassified Information (CUI) as defined by 32 CFR Part 2002. However, data exists within the environment that could reasonably qualify as CUI if properly designated by the contracting agency.**

#### 5.2 Rationale

| Factor | Finding |
|--------|---------|
| CUI markings on documents | None found |
| Prime contractor designation | No formal CUI designation communicated |
| Contract clause reference | DFARS clause present but no specific CUI categories identified |
| Data sensitivity | Infrastructure details and military tenant PII present — meets criteria for **potential** CUI |
| Agency designation | No evidence that the DoD contracting office has designated any information as CUI for this contract |

#### 5.3 Risk of CUI Being Present

| Scenario | Likelihood | Impact |
|----------|:----------:|:------:|
| Military housing infrastructure details ARE CUI but unmarked | Medium | High — controls not fully implemented for data that may legally be CUI |
| Military tenant PII in government systems IS CUI | Low-Medium | High — Privacy Act PII may be CUI depending on agency designation |
| CUI exists in unstructured data not reviewed (e.g., email attachments) | Medium | Medium — hard to find but limited in scope |
| No CUI exists (current assessment is correct) | Medium | Low — conservative approach already applied |

---

### 6. Assessment Adaptations

Because CUI may be present but unmarked, the following adaptations apply:

#### 6.1 Conservative Approach

Until CUI designation is formally clarified by the contracting agency:

| Action | Rationale |
|--------|-----------|
| All data received under the DoD contract is **treated as CUI** for assessment purposes | Conservative approach protects against undesignated CUI |
| The CUI boundary includes all systems that process contract data | Broadest defensible scope |
| All 110 NIST SP 800-171 controls apply in full | No control reduction based on CUI absence |

#### 6.2 Recommendations to the Organization

| # | Recommendation | Priority |
|:-:|----------------|:--------:|
| 1 | **Request CUI designation letter** from prime contracting officer confirming whether CUI exists under the contract | High |
| 2 | **Implement CUI marking training** for all employees who handle contract documents (AT-3) | High |
| 3 | **Conduct data inventory scan** to identify documents with potential CUI characteristics (military base data, infrastructure specs, tenant PII in government context) | Medium |
| 4 | **Engage prime contractor** to clarify DFARS flow-down and whether CDI is in scope | High |
| 5 | **Include CUI identification in annual security awareness training** | Medium |

---

### 7. Data Categories — Final Classification for Assessment

| Data Type | Assessment Classification | Rationale |
|-----------|:------------------------:|-----------|
| Military housing infrastructure details | **Treated as CUI** | Conservative approach; meets CUI Registry criteria for Critical Infrastructure |
| Tenant PII (military families) | **Treated as CUI** | Conservative approach; possible Privacy Act CUI |
| Contract terms and pricing | **Treated as CUI** | Conservative approach; possible Procurement CUI |
| Tenant PII (civilian, non-government) | **PII (non-CUI)** | No government nexus for civilian tenants |
| Employee PII | **PII (non-CUI)** | Standard HR data; no government nexus |
| Construction blueprints (non-military) | **Operational (non-CUI)** | Standard business data |
| Financial records (non-contract) | **Operational (non-CUI)** | Standard business data |

---

### 8. Conclusion

Based on the evidence available:

1. **No formally designated CUI** was identified in the environment during this phase.
2. **Potential CUI exists** in the form of military housing infrastructure details and military tenant PII.
3. **Conservative approach applied:** All potential CUI data is treated as CUI for the remainder of this assessment.
4. **Recommendation:** The organization should formally confirm CUI status with the prime contractor and contracting officer before the formal third-party assessment.

This determination should be reviewed and updated if new evidence of CUI designation emerges.

---

*Document Version: 1.0*
*Date: July 13, 2026*
