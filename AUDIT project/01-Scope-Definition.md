# Assessment Scope Definition

## Confidential — NIST SP 800-171 Readiness Assessment

---

### 1. Purpose

This document defines the precise boundary of the NIST SP 800-171 readiness assessment. It identifies the locations, systems, personnel, and data types that fall within the assessment scope and, equally important, what is explicitly excluded.

This scope definition must be reviewed and approved by the Executive Sponsor before assessment activities commence. Any proposed changes to scope during the engagement must be submitted in writing and approved through the change control process defined in the Project Planning Document.

---

### 2. In-Scope Locations

| Location | Type | Justification |
|----------|------|---------------|
| **Head Office** | Permanent administrative office | Primary location for executive, finance, IT, and administrative operations. Houses file server, network infrastructure, and administrative workstations. |
| **Property Management Office — Military Housing Community A** | On-site management office | Processes tenant PII, lease agreements, and potential CUI related to military housing occupancy. |
| **Property Management Office — Military Housing Community B** | On-site management office | Same as above. |
| **Employee Home Offices / Remote Work Locations** | Remote | Employees accessing organizational systems from home or field locations are within scope for remote access controls, endpoint security, and acceptable use. |

**Note:** Active construction sites are explicitly excluded (see Section 6). While construction project managers visit sites, all data processing occurs from the head office or remote access. Construction sites contain no IT infrastructure, data storage, or network connectivity related to the CUI environment.

---

### 3. In-Scope Systems

The following systems are within the assessment scope because they process, store, or transmit data types covered by NIST SP 800-171:

| System | Type | Data Handled | CUI Relevance |
|--------|------|--------------|:-------------:|
| **Microsoft 365** (Exchange Online, SharePoint, Teams, OneDrive) | Cloud SaaS | Email, documents, collaboration files, contracts | Potential CUI transit and storage |
| **Property Management SaaS** | Cloud SaaS | Tenant PII, lease agreements, rent records, maintenance history, occupancy data | Potential CUI (military tenant data) |
| **Accounting / ERP System** | On-premises / Cloud | Employee PII, payroll, financial records, vendor data | Employee PII (non-CUI but regulated) |
| **Network-Attached Storage (NAS) / File Server** | On-premises | Blueprints, contracts, policies, operational documents | Potential CUI storage |
| **VPN / Remote Access Solution** | Network Infrastructure | Encrypted tunnel for remote access to internal resources | Enables secure remote access; relevant to access control family |
| **Company-Issued Endpoints** (Laptops, Desktops) | Endpoint | All data types processed by assigned users | Primary user interface to CUI/PII |
| **Company-Managed Mobile Devices** | Endpoint | Email, property management app access, communication | Mobile access to tenant data and potential CUI |
| **Network Infrastructure** (Firewall, Switches, Wi-Fi) | Network Infrastructure | All network traffic within scope boundary | Foundational security control point |

---

### 4. In-Scope Personnel

All 20 employees are within the assessment scope. The rationale:

| Role Category | Count | Scope Rationale |
|---------------|:-----:|-----------------|
| **Executive** | 2 | Access to contracts, strategic documents, financial data |
| **IT** | 2 | Administrative access to all systems |
| **Construction Management** | 5 | Access to email, project documents, potential CUI in blueprints/specs |
| **Property Management** | 6 | Direct handlers of tenant PII and potential CUI |
| **Administration & Finance** | 5 | Access to employee PII, financial data, contracts |

**Assessment Activities Involving Personnel:**

- Policy and procedure awareness interviews (all roles)
- Technical control testing (IT personnel)
- Process walkthroughs (Property Management, Construction, Finance)
- Access control review (IT, Executive)

---

### 5. Data in Scope

| Data Category | Examples | Regulatory Driver |
|---------------|----------|-------------------|
| **Tenant PII** | Names, SSN, driver's license, financial records, lease agreements, background checks | State data breach laws, contract requirements |
| **Employee PII** | Names, SSN, payroll, tax forms, HR records | State data breach laws |
| **DoD Contract Data** | Contract terms, deliverables, pricing, reporting requirements | DFARS 252.204-7012 |
| **Potential CUI** | Military housing specifications, base infrastructure details, occupancy data, security-related facility information | NIST SP 800-171, DFARS |
| **Business Financial Data** | Accounting records, vendor payments, operational costs | Internal (not regulatory, but within boundary) |

**CUI Determination:** A definitive determination of whether specific data types constitute formal CUI will be made during Phase 8 (CUI Identification). Until then, data that is reasonably believed to be CUI will be treated as CUI for assessment purposes (conservative approach).

---

### 6. Explicit Exclusions

| Exclusion | Rationale |
|-----------|-----------|
| **Active Construction Sites** | Temporary locations with no IT infrastructure, no data storage, no network connectivity to organizational systems. Construction managers access systems remotely from these sites (covered under remote access controls in scope). |
| **Construction Subcontractors** | No access to organizational IT systems or data. Subcontractors receive work orders via email or phone but do not have accounts, credentials, or system access. |
| **Physical Access Control Systems** (key card systems, gate controls at properties) | Operate on isolated, air-gapped systems not connected to the corporate IT network. Do not process, store, or transmit CUI or PII covered by this assessment. |
| **Personal Devices Not Used for Work** | BYOD devices used exclusively for personal purposes are out of scope. BYOD devices used for work (e.g., personal phone checking work email) are in scope for applicable controls (MDM, acceptable use). |
| **Corporate Website / Public-Facing Marketing Systems** | Public-facing systems with no authentication, no data collection, and no connection to internal systems. |
| **Penetration Testing** | This engagement is a readiness assessment, not a penetration test. Technical verification will focus on control implementation review, not active exploitation. Penetration testing is recommended as a future activity. |

---

### 7. Scope Diagram

The following diagram illustrates the assessment boundary:

```
                         ┌─────────────────────────────────────┐
                         │        ASSESSMENT BOUNDARY          │
                         │                                     │
                         │  ┌───────────────────────────────┐  │
                         │  │      HEAD OFFICE              │  │
                         │  │  ┌─────┐ ┌──────┐ ┌───────┐  │  │
                         │  │  │ NAS │ │  ERP │ │ 365   │  │  │
                         │  │  └─────┘ └──────┘ └───────┘  │  │
                         │  │         ┌──────────┐         │  │
                         │  │         │ Firewall │         │  │
                         │  │         └──────────┘         │  │
                         │  └───────────────────────────────┘  │
                         │                                     │
  ┌──────────────┐       │  ┌───────────────────────────────┐  │       ┌──────────────────┐
  │  Military    │       │  │  PROPERTY MGMT OFFICES        │  │       │  CLOUD SERVICES   │
  │  Housing     │◄──────┼──┤  ┌──────────┐                │  ├───────┤  ┌──────────┐    │
  │  Tenants     │       │  │  │ MGMT PC  │                │  │       │  │ M365     │    │
  └──────────────┘       │  │  └──────────┘                │  │       │  └──────────┘    │
                         │  └───────────────────────────────┘  │       │  ┌──────────┐    │
                         │                                     │       │  │ PM SaaS  │    │
                         │  ┌───────────────────────────────┐  │       │  └──────────┘    │
                         │  │  REMOTE / FIELD EMPLOYEES     │  │       └──────────────────┘
                         │  │  ┌────────┐ ┌───────┐        │  │
                         │  │  │Laptop  │ │ Phone │        │  │
                         │  │  └────────┘ └───────┘        │  │
                         │  └───────────────────────────────┘  │
                         │                                     │
                         └─────────────────────────────────────┘

                              ┌─────────────────────┐
                              │   EXCLUDED          │
                              │  ┌───────────────┐  │
                              │  │ Construction  │  │
                              │  │ Sites         │  │
                              │  └───────────────┘  │
                              │  ┌───────────────┐  │
                              │  │ Subs (no sys  │  │
                              │  │ access)       │  │
                              │  └───────────────┘  │
                              └─────────────────────┘
```

---

### 8. Scope Assumptions and Caveats

1. **Tenant PII** in the Property Management SaaS is assumed to include data elements that may qualify as CUI when associated with military housing contracts. This will be verified in Phase 8.
2. **Cloud service providers** (Microsoft 365, Property Management SaaS vendor) are treated as system components for control assessment purposes. Their security posture will be evaluated through available evidence (SOC 2 reports, contractual terms, vendor questionnaires).
3. **The IT Managed Service Provider (MSP)** is not in scope as a separate entity, but the organization's management and oversight of the MSP relationship is in scope.
4. **Personal mobile devices** using BYOD for email access are considered in scope only for policies and controls that apply to device-level access to organizational data.

---

### 9. Scope Approval

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Lead Consultant | [Consultant Name] | | |
| Executive Sponsor | [Client Name] | | |

---

*Document Version: 1.0*
*Date: July 13, 2026*
