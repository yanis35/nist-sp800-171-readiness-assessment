# Asset Inventory

## Confidential — NIST SP 800-171 Readiness Assessment

---

### 1. Inventory Summary

| Category | Count | CUI Assets | PII Assets |
|----------|:-----:|:----------:|:----------:|
| Servers | 1 | 1 | 1 |
| Network Infrastructure | 4 | 0 | 0 |
| Endpoints (Company) | 20 | 20 | 20 |
| Mobile Devices (Company) | 5 | 0 | 5 |
| Mobile Devices (BYOD) | ~12 | 0 | 12 |
| Cloud Services | 3 | 2 | 3 |
| Data Assets | 5 | 3 | 4 |
| User / Identity Assets | ~25 | — | — |
| **Total** | **~70** | | |

---

### 2. Servers

| Asset ID | Name | Type | Location | Owner | CUI? | PII? | OS / Version | Notes |
|----------|------|------|----------|-------|:----:|:----:|--------------|-------|
| SRV-NAS-001 | NAS / File Server | On-prem file server | Head Office — Server Closet | IT Manager | **Yes** | **Yes** | Linux-based / v5.x | Primary CUI document repository; shared access via SMB/CIFS; contains contract docs, blueprints, policies, HR records |

---

### 3. Network Infrastructure

| Asset ID | Name | Type | Location | Owner | CUI? | PII? | Firmware | Notes |
|----------|------|------|----------|-------|:----:|:----:|----------|-------|
| NET-FW-001 | Edge Firewall | Firewall / VPN Gateway | Head Office — Server Closet | IT Manager | No | No | v7.x | Primary network boundary defense; VPN termination; NAT; access rules |
| NET-SW-001 | Managed Switch (Core) | Layer 3 Switch | Head Office — Server Closet | IT Manager | No | No | v6.x | LAN backbone; VLAN segmentation |
| NET-SW-002 | Managed Switch (Property Office A) | Layer 2 Switch | Property Office A | IT Manager (remote mgmt) | No | No | v5.x | Local LAN for property office workstations |
| NET-AP-001 | Wi-Fi Access Point | Wireless AP | Head Office | IT Manager | No | No | v6.x | Segmented SSIDs (corporate / guest) |

---

### 4. Endpoints — Company-Issued

#### 4.1 Head Office Workstations

| Asset ID | Name / User | Type | Location | Owner | CUI? | PII? | OS | Notes |
|----------|-------------|------|----------|-------|:----:|:----:|-----|-------|
| HQ-WKS-001 | CEO Workstation | Desktop | Head Office — Executive Office | CEO | **Yes** | **Yes** | Windows 11 | Executive access to all systems |
| HQ-WKS-002 | Operations Director Workstation | Desktop | Head Office — Executive Office | Ops Director | **Yes** | **Yes** | Windows 11 | Contract management, project oversight |
| HQ-WKS-003 | IT Admin Workstation | Desktop | Head Office — IT Office | IT Manager | **Yes** | **Yes** | Windows 11 | Admin access; server management; elevated privileges |
| HQ-WKS-004 | IT Support Workstation | Desktop | Head Office — IT Office | IT Support | **Yes** | **Yes** | Windows 11 | Help desk; user support |
| HQ-WKS-005 | Finance Workstation | Desktop | Head Office — Finance | Finance Manager | No | **Yes** | Windows 11 | Accounting ERP; payroll; financial data |
| HQ-WKS-006 | Admin Assistant Workstation | Desktop | Head Office — Admin | Admin Assistant | **Yes** | **Yes** | Windows 10 | Contract admin; document management |
| HQ-WKS-007 | Construction Manager Workstation | Desktop | Head Office — Construction | Construction Mgr | **Yes** | No | Windows 11 | Project management; blueprints; contractor coordination |
| HQ-WKS-008 | Design / Planning Workstation | Desktop | Head Office — Construction | Designer | **Yes** | No | Windows 10 | CAD / design software; blueprint storage |

#### 4.2 Property Office Workstations

| Asset ID | Name / User | Type | Location | Owner | CUI? | PII? | OS | Notes |
|----------|-------------|------|----------|-------|:----:|:----:|-----|-------|
| PM-WKS-001 | Property Manager A | Desktop | Property Office A | Property Mgr A | **Yes** | **Yes** | Windows 10 | PM SaaS; M365; tenant management |
| PM-WKS-002 | Property Admin A | Desktop | Property Office A | Admin A | **Yes** | **Yes** | Windows 10 | Leasing; tenant records |
| PM-WKS-003 | Property Manager B | Desktop | Property Office B | Property Mgr B | **Yes** | **Yes** | Windows 10 | PM SaaS; M365; tenant management |
| PM-WKS-004 | Maintenance Coordinator | Desktop | Property Office B | Maint Coord | **Yes** | **Yes** | Windows 10 | Work order system; tenant PII access |

#### 4.3 Field Laptops

| Asset ID | Name / User | Type | Location | Owner | CUI? | PII? | OS | Notes |
|----------|-------------|------|----------|-------|:----:|:----:|-----|-------|
| LAP-001 | Construction PM Laptop | Laptop | Field / Remote | Construction PM 1 | **Yes** | No | Windows 11 | VPN access; project management; field use |
| LAP-002 | Construction PM Laptop | Laptop | Field / Remote | Construction PM 2 | **Yes** | No | Windows 11 | VPN access; project management; field use |
| LAP-003 | Construction Site Supervisor Laptop | Laptop | Field / Remote | Site Supervisor 1 | **Yes** | No | Windows 10 | VPN access; construction docs; field use |
| LAP-004 | Construction Site Supervisor Laptop | Laptop | Field / Remote | Site Supervisor 2 | **Yes** | No | Windows 10 | VPN access; construction docs; field use |
| LAP-005 | IT Portable Laptop | Laptop | Field / Remote | IT Support | **Yes** | **Yes** | Windows 11 | On-call support; admin access; portable troubleshooting |
| LAP-006 | Ops Director Laptop | Laptop | Field / Remote | Ops Director | **Yes** | **Yes** | Windows 11 | Travel; site visits; remote access |
| LAP-007 | Finance Laptop (remote) | Laptop | Remote | Finance (remote staff) | No | **Yes** | Windows 10 | Occasional remote work; ERP access |
| LAP-008 | Admin Remote Laptop | Laptop | Remote | Admin (remote staff) | **Yes** | **Yes** | Windows 10 | Remote contract admin |

---

### 5. Mobile Devices

#### 5.1 Company-Issued Mobile Devices

| Asset ID | Name / User | Type | Owner | CUI? | PII? | OS | Notes |
|----------|-------------|------|-------|:----:|:----:|-----|-------|
| MOB-001 | CEO Mobile | Smartphone | CEO | No | **Yes** | iOS | Company plan; M365 email; Teams |
| MOB-002 | Property Manager A Mobile | Smartphone | Property Mgr A | No | **Yes** | iOS | Company plan; M365 email; PM SaaS app |
| MOB-003 | Property Manager B Mobile | Smartphone | Property Mgr B | No | **Yes** | iOS | Company plan; M365 email; PM SaaS app |
| MOB-004 | Construction Manager Mobile | Smartphone | Construction Mgr | No | No | Android | Company plan; email; Teams |
| MOB-005 | Maintenance Coordinator Mobile | Smartphone | Maint Coord | No | **Yes** | Android | Company plan; email; work order app |

#### 5.2 BYOD Mobile Devices (Approx.)

| Asset ID | Name | Count | Owner | CUI? | PII? | Notes |
|----------|------|:-----:|-------|:----:|:----:|-------|
| BYOD-POOL | Personal smartphones used for work email / Teams | ~10-12 | Employees | No | **Yes** | Microsoft 365 mobile app; Conditional Access policies apply; no device management enforced; significant risk |

---

### 6. Cloud Services

| Asset ID | Name | Type | Provider | CUI? | PII? | Data Stored | Auth Method | Notes |
|----------|------|------|----------|:----:|:----:|-------------|-------------|-------|
| CLOUD-M365 | Microsoft 365 Business Premium | SaaS | Microsoft | **Yes** | **Yes** | Email, documents, Teams messages, OneDrive files | Azure AD + MFA | Multiple plans; includes Exchange, SharePoint, Teams, OneDrive, Defender |
| CLOUD-PMS | Property Management SaaS | SaaS | Third-Party Vendor | **Yes** | **Yes** | Tenant records, lease agreements, financial transactions, occupancy data | Vendor Auth + MFA | Most critical PII/CUI repository; vendor security posture unknown |
| CLOUD-ERP | Accounting / ERP System | SaaS / On-prem | Third-Party / Self-hosted | No | **Yes** | Employee PII, payroll, financial records | Local Auth + MFA | May be on-prem with cloud sync; verify architecture |

---

### 7. Software Assets

| Asset ID | Name | Type | Licenses / Users | Versions | CUI? | Notes |
|----------|------|------|:----------------:|----------|:----:|-------|
| SW-001 | Microsoft 365 Business Premium | Productivity Suite | 25 users | Latest | **Yes** | Includes Office desktop apps, Exchange, SharePoint, Teams, OneDrive, Defender |
| SW-002 | Property Management SaaS | Property Mgmt | 10 users | SaaS (latest) | **Yes** | Web-based; vendor-managed |
| SW-003 | Accounting ERP | Accounting | 5 users | v2024 | No | On-prem / cloud hybrid |
| SW-004 | Project Management Tool | PM Software | 8 users | SaaS (latest) | **Yes** | Construction scheduling; contract milestone tracking |
| SW-005 | VPN Client | Remote Access | 15 users | Latest | No | Installed on all company laptops |
| SW-006 | Antivirus / EDR | Security | 25 endpoints | Latest | No | License for all company-managed endpoints |
| SW-007 | CAD / Design Software | Design | 2 users | v2024 | **Yes** | Blueprints; construction specs |
| SW-008 | Windows 10 / 11 Pro | OS | 20 workstations | 22H2+ | No | Company-managed endpoints |
| SW-009 | iOS / Android | Mobile OS | ~17 devices | Latest | No | Mix of company and BYOD |

---

### 8. Data Assets

| Asset ID | Name | Type | Location | Size | CUI? | PII? | Backup? | Notes |
|----------|------|------|----------|:----:|:----:|:----:|:-------:|-------|
| DATA-NAS-001 | NAS — Contracts & CUI Share | File Share | NAS Volume 1 | ~500 GB | **Yes** | **Yes** | Yes — nightly | DoD contracts, blueprints, military housing specs, HR records |
| DATA-NAS-002 | NAS — Corporate Operations Share | File Share | NAS Volume 2 | ~200 GB | No | No | Yes — nightly | Policies, procedures, operational docs, templates |
| DATA-M365-001 | SharePoint — Corporate Documents | Document Library | Microsoft 365 | ~100 GB | **Yes** | **Yes** | Yes (SaaS) | Active collaboration; version history; shared with external parties |
| DATA-M365-002 | Exchange Online — Mailboxes | Email | Microsoft 365 | ~50 GB total | **Yes** | **Yes** | Yes (SaaS) | Contains CUI in email attachments and body; legal hold considerations |
| DATA-PMS-001 | PM SaaS — Tenant Database | Database | PM SaaS Cloud | Unknown | **Yes** | **Yes** | Yes (SaaS) | Most sensitive structured data repository; tenant PII + potential CUI |

---

### 9. User / Identity Assets

| Asset ID | Type | Count | System | CUI Access? | Notes |
|----------|------|:-----:|--------|:-----------:|-------|
| ID-AD-001 | Active Directory User Accounts | 20 | On-prem AD + Azure AD Sync | **Yes** | Primary identity source; synced to Azure AD for M365 |
| ID-AD-002 | Local Admin Accounts | 2 | NAS, Workstations | **Yes** | IT personnel only; elevated privileges |
| ID-AD-003 | Service Accounts | 3 | NAS, Backup, ERP | **Yes** | Automated processes; no interactive logon |
| ID-AD-004 | MSP Admin Accounts | 2 | Firewall, Server, M365 Admin | **Yes** | External privileged access; dedicated accounts |
| ID-AD-005 | Break-Glass / Emergency Accounts | 1 | On-prem AD | **Yes** | Emergency access; stored in safe |
| ID-PMS-001 | PM SaaS User Accounts | 10 | Property Management SaaS | **Yes** | Role-based access within application |
| ID-M365-001 | Azure AD Guest Accounts | ~3-5 | Microsoft 365 | **Yes** | External collaboration partners (architect, accountant, legal) |

---

### 10. Asset Inventory Reconciliation

| Data Source | Reliability | Last Updated | Gaps Identified |
|-------------|:-----------:|:------------:|-----------------|
| Client-provided inventory list | Medium | Unknown | Likely missing BYOD devices, some cloud services, and mobile devices |
| M365 Admin Center export | High | Real-time | Does not include on-prem assets or non-M365 SaaS |
| Network scan (if available) | High | Point-in-time | Only discovers online assets; may miss offline endpoints |
| Physical walkthrough | High | Assessment date | Requires site access; best source for hidden/unofficial assets |
| Personnel interviews | Medium | Interview date | Self-reported; may miss devices employees forget to mention |

**Note:** This inventory is based on available information and reasonable assumptions. A physical walkthrough and network scan should be conducted to validate and reconcile this inventory before finalizing the assessment.

---

*Document Version: 1.0*
*Date: July 13, 2026*
