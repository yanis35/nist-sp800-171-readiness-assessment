# System Boundary Definition

## Confidential — NIST SP 800-171 Readiness Assessment

---

### 1. Purpose

This document defines the **Security Protection Asset (SPA)** boundary for the CUI environment. The system boundary establishes the exact technical and logical perimeter within which NIST SP 800-171 security requirements are assessed and enforced.

All systems, users, and data flows inside this boundary are subject to the 113 security requirements of NIST SP 800-171 Rev 2.

---

### 2. System Boundary Narrative

The organization's CUI environment spans three physical locations and two cloud tenants, connected through encrypted tunnels and internet-based SaaS access. The boundary is primarily **logical** — defined by authentication, encryption, and access control — rather than purely physical, due to the significant cloud and remote workforce components.

**At a high level:**

The head office serves as the core of the boundary. It houses the on-premises file server (the primary storage for contract documents and potential CUI), the accounting ERP, and the network gateway. From here, site-to-site encrypted tunnels extend the boundary to property management offices. Cloud tenants (Microsoft 365 and Property Management SaaS) are considered **extensions of the boundary** — they are not trusted external entities but rather system components subject to the same control requirements. Remote and field employees extend the boundary to their physical location through encrypted VPN connections to the head office and authenticated SaaS access from managed endpoints.

The boundary is not the entire company. General-purpose corporate systems that do not process, store, or transmit CUI are logically or physically separated from the CUI environment.

---

### 3. System Boundary Diagram

```
╔══════════════════════════════════════════════════════════════════╗
║                    CUI SYSTEM BOUNDARY                          ║
║                                                                  ║
║  ┌─────────────────────────────────────────────────────────┐    ║
║  │                   HEAD OFFICE                           │    ║
║  │                                                         │    ║
║  │  ┌──────────┐  ┌──────────┐  ┌──────────────────────┐  │    ║
║  │  │ Firewall │──│  Switch  │──│    Wi-Fi AP          │  │    ║
║  │  │ (edge)   │  │ (LAN)    │  │ (segmented SSID)     │  │    ║
║  │  └────┬─────┘  └────┬─────┘  └──────────────────────┘  │    ║
║  │       │             │                                   │    ║
║  │       │    ┌────────┴────────┐                          │    ║
║  │       │    │   NAS / File    │                          │    ║
║  │       │    │   Server (CUI)  │                          │    ║
║  │       │    └─────────────────┘                          │    ║
║  │       │    ┌─────────────────┐                          │    ║
║  │       │    │  Accounting ERP │                          │    ║
║  │       │    │  (PII, non-CUI) │                          │    ║
║  │       │    └─────────────────┘                          │    ║
║  │       │    ┌─────────────────┐                          │    ║
║  │       └────│ Admin Workstations (x8)                   │    ║
║  │            └─────────────────┘                          │    ║
║  └─────────────────────────────────────────────────────────┘    ║
║                                                                  ║
║  ┌─────────────────────────────────────────────────────────┐    ║
║  │          PROPERTY MANAGEMENT OFFICES (x2)               │    ║
║  │                                                         │    ║
║  │  ┌──────────────┐     ┌──────────────────────────┐      │    ║
║  │  │ Workstation  │─────│ Internet → Cloud SaaS    │      │    ║
║  │  │ (browser)    │     │ (M365, PM SaaS)          │      │    ║
║  │  └──────────────┘     └──────────────────────────┘      │    ║
║  └─────────────────────────────────────────────────────────┘    ║
║                                                                  ║
║  ┌─────────────────────────────────────────────────────────┐    ║
║  │              CLOUD TENANTS (Shared Responsibility)       │    ║
║  │                                                         │    ║
║  │  ┌──────────────────┐    ┌──────────────────────┐       │    ║
║  │  │ Microsoft 365    │    │ Property Mgmt SaaS   │       │    ║
║  │  │ • Exchange Online │    │ • Tenant DB (PII)   │       │    ║
║  │  │ • SharePoint      │    │ • Lease Records     │       │    ║
║  │  │ • OneDrive        │    │ • Occupancy Data    │       │    ║
║  │  │ • Teams           │    │ • Potential CUI     │       │    ║
║  │  │ • Potential CUI   │    └──────────────────────┘       │    ║
║  │  └──────────────────┘                                    │    ║
║  └─────────────────────────────────────────────────────────┘    ║
║                                                                  ║
║  ┌─────────────────────────────────────────────────────────┐    ║
║  │         REMOTE / FIELD USERS (x12 approx.)              │    ║
║  │                                                         │    ║
║  │  ┌─────────┐     ┌──────────┐     ┌───────────────┐     │    ║
║  │  │ Laptop  │─────│ VPN      │─────│ Head Office   │     │    ║
║  │  │ (CUI)   │     │ (encrypt)│     │ / Cloud       │     │    ║
║  │  └─────────┘     └──────────┘     └───────────────┘     │    ║
║  │  ┌─────────┐                                            │    ║
║  │  │ Mobile  │─────(direct to cloud via authenticated app)│    ║
║  │  │ (BYOD)  │                                            │    ║
║  │  └─────────┘                                            │    ║
║  └─────────────────────────────────────────────────────────┘    ║
║                                                                  ║
║  ┌─────────────────────────────────────────────────────────┐    ║
║  │          IT MSP (PRIVILEGED ACCESS)                     │    ║
║  │                                                         │    ║
║  │  ┌──────────────┐     ┌──────────────────────────┐      │    ║
║  │  │ MSP Technicians│───│ Remote Admin Access       │      │    ║
║  │  │ (external)    │    │ (firewall, server, M365) │      │    ║
║  │  └──────────────┘     └──────────────────────────┘      │    ║
║  └─────────────────────────────────────────────────────────┘    ║
║                                                                  ║
╚══════════════════════════════════════════════════════════════════╝
```

---

### 4. Components Inside the Boundary

| Component | Type | CUI/PII | Location | Notes |
|-----------|------|:-------:|----------|-------|
| **NAS / File Server** | On-prem server | **Yes (CUI)** | Head Office | Primary CUI document repository; requires access controls, audit logging, encryption |
| **Accounting ERP** | On-prem / Hybrid | PII only | Head Office | Employee PII; within boundary because it shares network and authentication |
| **Head Office Workstations** (x8) | Endpoint | **Yes (CUI)** | Head Office | Administrative users; access to all systems |
| **Property Mgmt Workstations** (x4) | Endpoint | **Yes (PII / CUI)** | Property Offices | Browser-based access to SaaS; no local CUI storage expected |
| **Field Laptops** (x8) | Endpoint | **Yes (CUI)** | Remote / Field | VPN access to file server; local CUI caching possible |
| **Company Mobile Devices** (x5) | Mobile | PII / CUI access | Remote / Field | Email and SaaS app access; no local CUI storage |
| **BYOD Mobile Devices** (approx. 10-15) | Mobile | Email only | Remote / Field | Conditional access policies apply |
| **Firewall** | Network | N/A | Head Office | Boundary defense; VPN endpoint; traffic filtering |
| **Managed Switch** | Network | N/A | Head Office | LAN segmentation |
| **Wi-Fi Access Point** | Network | N/A | Head Office | Segmented SSID for CUI traffic |
| **Microsoft 365 Tenant** | Cloud SaaS | **Yes (CUI)** | Cloud | Email, documents, collaboration |
| **Property Management SaaS** | Cloud SaaS | **Yes (PII / CUI)** | Cloud | Tenant database, lease records |

---

### 5. Components Outside the Boundary

| Component | Rationale for Exclusion |
|-----------|------------------------|
| **Construction Sites (physical locations)** | No IT infrastructure; no data storage; no network connectivity to organizational systems |
| **Construction Subcontractor Systems** | No organizational accounts or system access |
| **Personal Devices (non-work)** | No organizational data; no access to organizational systems |
| **Corporate Website / Public Marketing** | Internet-facing only; no authentication; no data processing |
| **Physical Access Control Systems (property gates, key fobs)** | Air-gapped; not connected to IT network |

---

### 6. Boundary Defense Mechanisms

| Control | Mechanism | Location |
|---------|-----------|----------|
| **Network Segmentation** | Internal VLAN segmentation; guest Wi-Fi isolated from corporate LAN | Head Office |
| **Firewall** | Stateful inspection; inbound/outbound rule sets; VPN termination | Head Office edge |
| **VPN** | IPSec or SSL VPN with encrypted tunnel for remote access | Firewall / Client |
| **MFA** | Multi-factor authentication for remote access, cloud admin, and SaaS | All remote access + cloud |
| **Cloud Tenant Security** | Microsoft 365 Defender, Conditional Access, DLP policies | Cloud |
| **Endpoint Protection** | Antivirus/EDR on company-managed endpoints | All endpoints |
| **Authentication** | Active Directory / Azure AD; password policies; account lockout | Directory level |

---

### 7. Cloud Boundary Considerations

Cloud services introduce a **shared responsibility model**. The system boundary extends to include cloud tenants, but responsibility is divided:

| Responsibility | Organization | Cloud Provider |
|----------------|:------------:|:--------------:|
| Data classification and labeling | ✓ | |
| User access management (IAM) | ✓ | |
| Client-side encryption | ✓ | |
| Application-level security (SaaS config) | ✓ | |
| Physical data center security | | ✓ |
| Infrastructure security (hypervisor, network) | | ✓ |
| Platform security (for SaaS) | | ✓ |
| Compliance certifications (SOC 2, FedRAMP) | | ✓ |

**Assessment Approach:** The organization's configuration and management of cloud services is in scope. Cloud provider controls are assessed through review of available SOC 2 reports, FedRAMP authorization letters, and contractual terms. The organization's responsibility for cloud security is a key focus area.

---

### 8. User Types and Access Paths

| User Type | Location | Primary Systems | Access Method | Authentication |
|-----------|----------|----------------|---------------|----------------|
| **Executive** | Head Office | M365, ERP, PM SaaS | Local LAN + browser | Password + MFA (cloud) |
| **IT Administrator** | Head Office / Remote | All systems | LAN + VPN + RDP | Password + MFA |
| **Construction Manager** | Head Office / Field | M365, PM tool, NAS | LAN or VPN | Password + MFA (remote) |
| **Property Manager** | Property Office / Field | PM SaaS, M365 | Internet (browser) | Password + MFA |
| **Admin / Finance** | Head Office | M365, ERP, PM SaaS | Local LAN + browser | Password + MFA (cloud) |
| **MSP Technician** | External | Firewall, Server, M365 admin | Remote admin VPN | Dedicated admin account + MFA |

---

### 9. Key Findings for Assessment

The following boundary characteristics will drive specific control testing:

1. **Cloud services are the dominant attack surface.** More data lives in M365 and PM SaaS than on-premises. Cloud security configuration is critical.

2. **Remote workforce expands the boundary significantly.** 60% of users access CUI/PII from outside the head office. Endpoint security, VPN, and MFA are high-priority findings areas.

3. **The MSP has privileged access to the entire boundary.** MSP access controls, monitoring, and contractual security requirements must be assessed.

4. **BYOD creates a fuzzy boundary edge.** Personal phones accessing corporate email extend the boundary to unmanaged devices. Conditional access and data loss prevention are critical compensating controls.

---

*Document Version: 1.0*
*Date: July 13, 2026*
