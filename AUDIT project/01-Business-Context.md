# Business Context

## Confidential — NIST SP 800-171 Readiness Assessment

---

### 1. Operational Model

The organization operates across three distinct operational environments:

| Environment | Description | Primary Activities |
|-------------|-------------|-------------------|
| **Head Office** | Central administrative office | Executive management, finance, contract administration, IT operations, design & planning |
| **Construction Sites** | Active residential development locations (varies — typically 1-3 concurrent sites) | Construction project management, contractor coordination, site supervision |
| **Managed Properties** | Completed residential communities, including military housing | Leasing, tenant management, maintenance coordination, rent collection |

**Operational Flow:**

The design and planning team works from the head office. Once designs are approved, construction project managers split time between the head office and active construction sites. Upon project completion, properties are transferred to the property management team, which operates primarily from an on-site management office at each community.

---

### 2. Workforce Profile

| Work Type | Approx. % of Workforce | Roles |
|-----------|:----------------------:|-------|
| **Office-Based (Head Office)** | 40% | Executive, Administration, Finance, IT, Design |
| **Field-Based (Construction Sites)** | 25% | Construction Project Managers, Site Supervisors |
| **Field-Based (Managed Properties)** | 30% | Property Managers, Maintenance Coordinators |
| **Remote / Occasional** | 5% | Select administrative staff |

**Key Observation for Assessment:**

The workforce is not primarily desk-bound. Approximately 60% of employees work outside the head office environment, which has direct implications for:

- Endpoint security (laptops, tablets, mobile phones)
- Remote access controls
- Data storage and synchronization
- Acceptable use policies
- Mobile device management

---

### 3. Technology Dependencies

| System / Tool | Purpose | User Base | Data Types |
|---------------|---------|-----------|------------|
| **Microsoft 365 (Exchange, SharePoint, Teams)** | Email, document collaboration, communication | All employees | PII, contracts, operational data |
| **Property Management SaaS** | Tenant records, lease agreements, rent collection, maintenance ticketing | Property Management, Finance | Tenant PII, financial records, lease data |
| **Accounting / ERP** | Payroll, accounts payable/receivable, financial reporting | Finance, Executive | Employee PII, financial data, vendor records |
| **Project Management Tool** | Construction scheduling, contractor coordination, milestone tracking | Construction, Executive | Project plans, contractor info, schedules |
| **File Storage / NAS** | Central file repository for blueprints, contracts, policies | All employees | Blueprints, contracts, policies, CUI (potential) |
| **Remote Access / VPN** | Secure remote access for field employees | Field-based employees | All data types during transit |
| **Mobile Devices (Company + BYOD)** | Email, property management app, communication | All employees | PII, operational data |

**Critical Dependency Note:**

The Property Management SaaS is the **single most critical system** for tenant data protection. It holds the largest concentration of PII and may contain CUI depending on what data is stored about military housing tenants.

---

### 4. Key Business Processes Involving Sensitive Data

| Process | Description | Data Involved | Systems Used |
|---------|-------------|---------------|--------------|
| **Tenant Onboarding** | Application, background check, lease signing, move-in | Tenant PII (SSN, employment, credit), lease agreements | Property Management SaaS, Email |
| **DoD Contract Bidding & Management** | Bid preparation, contract award, reporting, compliance documentation | Contract data, pricing, military housing specs, potential CUI | Email, File Storage, Project Management |
| **Payroll & HR** | Employee onboarding, payroll processing, benefits | Employee PII (SSN, banking, tax info) | Accounting ERP, Email |
| **Maintenance & Work Orders** | Tenant requests, contractor dispatch, completion verification | Tenant name, unit number, access records | Property Management SaaS, Email |
| **Construction Project Handover** | Transfer of completed units from construction to property management | Unit specs, warranty info, occupancy schedules | Project Management, File Storage, Email |

---

### 5. Third-Party Dependencies

| Third Party | Service Provided | Data Access | Risk Level |
|-------------|------------------|-------------|:----------:|
| **Property Management SaaS Vendor** | Cloud-hosted property management platform | Tenant PII, lease data, financials | **High** — direct access to sensitive data |
| **IT Managed Service Provider (MSP)** | Help desk, infrastructure support, network administration | Potential access to all systems and data | **High** — privileged access |
| **Construction Subcontractors** | Electrical, plumbing, framing, etc. | Minimal (site access only, no data systems) | **Low** — physical site only |
| **Background Check Service** | Tenant screening and credit checks | Tenant PII (SSN, credit history) | **High** — transmits sensitive data |
| **Accounting / Tax Preparer** | External bookkeeping, tax filing | Financial data, payroll data | **Medium** — financial PII |
| **Payroll Processor** | Payroll processing and tax filing | Employee PII (SSN, banking) | **High** — employee PII |
| **Cloud Infrastructure Providers** | Microsoft 365, SaaS hosting | All data stored in cloud services | **High** — data at rest |

---

### 6. Pain Points & Concerns

Based on industry knowledge and preliminary discussions, likely areas of concern include:

1. **Data Breach of Tenant PII** — The most immediate reputational and financial risk. A breach of military tenant data would have cascading consequences including DoD notification requirements under DFARS 252.204-7012.

2. **Loss of DoD Contract** — Non-compliance with NIST SP 800-171 could result in contract termination. For a 20-person organization, losing the military housing contract would represent a significant revenue impact.

3. **Ransomware / Business Interruption** — A ransomware incident encrypting the property management system or file server would halt tenant operations, rent collection, and maintenance coordination.

4. **Insider Threat / Accidental Exposure** — Small organizations often lack data classification training. An employee accidentally emailing tenant PII or CUI to the wrong recipient is a realistic scenario.

5. **Shadow IT** — Field employees may use personal devices, unauthorized cloud storage, or personal email to get work done faster, creating unmanaged data silos.

---

### 7. Business Context Impact on Assessment

The following factors will directly influence control testing and recommendations:

| Business Factor | Assessment Impact |
|----------------|-------------------|
| ~60% field-based workforce | Remote access controls, mobile device management, endpoint protection are critical |
| Heavy reliance on cloud SaaS | Vendor risk management, data residency, encryption at rest/transit |
| Small IT team (2 people) | Realistic limitations on administrative capacity; automation and simplicity needed |
| Construction sites are temporary | Fluctuating physical locations; fixed head office and property offices are the stable boundary |
| Single large customer (DoD) | Business continuity and incident response must consider contractual reporting timelines |

---

*Document Version: 1.0*
*Date: July 13, 2026*
