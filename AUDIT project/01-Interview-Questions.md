# Interview Questions

## Confidential — NIST SP 800-171 Readiness Assessment

---

### 1. Purpose

This document contains structured interview questions for each role within the assessment scope. Interviews serve to verify policy implementation, assess personnel awareness, identify gaps between documented policy and actual practice, and collect operational evidence.

**Interview Principles:**
- Questions are open-ended unless a specific yes/no verification is needed
- Follow-up probing is expected based on responses
- Responses are documented and cross-referenced to evidence items and controls
- Interviews are conducted with empathy — personnel are helping the assessment, not being tested

---

### 2. Executive Sponsor (CEO / Operations Director)

**Estimated Time:** 30 minutes
**Purpose:** Strategic perspective, compliance drivers, risk appetite, resource commitment

| # | Question | Type | Controls Addressed | Cross-Reference |
|:-:|----------|:----:|:------------------:|:--------------:|
| 1 | What is your understanding of why NIST SP 800-171 compliance is required for the organization? | Knowledge Check | AT 3.2.1 | EVD-AT-01 |
| 2 | How do you oversee cybersecurity at a strategic level? What reporting do you receive, and how often? | Behavioral | RA 3.11.1, CA 3.12.1 | EVD-RA-01 |
| 3 | What keeps you up at night from a cybersecurity perspective? What is your biggest concern? | Strategic | — | Context |
| 4 | How is cybersecurity funded and prioritized compared to other business needs? | Strategic | CA 3.12.2 | EVD-CA-02 |
| 5 | Walk me through what would happen if ransomware encrypted all your files tomorrow morning. | Process Walkthrough | IR 3.6.1, 3.6.2 | EVD-IR-01 |
| 6 | Have you signed off on any risk acceptance decisions related to security? If so, what and why? | Behavioral | CA 3.12.5 | EVD-CA-01 |
| 7 | How do you ensure that security requirements are communicated to and understood by all employees? | Behavioral | AT 3.2.1, 3.2.3 | EVD-AT-01 |
| 8 | What is your relationship with the DoD prime contractor regarding security compliance? Do they provide guidance or requirements directly? | Behavioral | — | Context |
| 9 | Are you aware of the DFARS 72-hour cyber incident reporting requirement? How would you ensure that is met? | Knowledge Check | IR 3.6.2 | EVD-IR-03 |
| 10 | What is your expectation of this readiness assessment? What outcome would make this valuable to you? | Strategic | — | Scope |

---

### 3. IT Manager

**Estimated Time:** 60 minutes (primary technical interview)
**Purpose:** Technical implementation, configuration, policies, incident response, operational security

#### 3.1 General & Policy

| # | Question | Type | Controls Addressed | Cross-Reference |
|:-:|----------|:----:|:------------------:|:--------------:|
| 1 | Can you describe the current IT environment — what systems, networks, and services are in scope for CUI? | Knowledge Check | CA 3.12.4 | EVD-CA-01 |
| 2 | What security policies and procedures currently exist? Which ones are formally approved and which are informal? | Knowledge Check | All families | EVD-AC-01, etc. |
| 3 | How is the IT function staffed? What is your capacity for security tasks versus daily operations? | Behavioral | — | Context |
| 4 | Who else has administrative access to your systems (internal and external)? | Behavioral | AC 3.1.5, 3.1.15 | EVD-AC-13 |

#### 3.2 Access Control (AC)

| # | Question | Type | Controls Addressed | Cross-Reference |
|:-:|----------|:----:|:------------------:|:--------------:|
| 5 | Walk me through how you provision access for a new employee. What happens on Day 1? | Process Walkthrough | AC 3.1.1, 3.1.2 | EVD-AC-01, EVD-AC-02 |
| 6 | How do you handle access revocation when an employee leaves or changes roles? | Process Walkthrough | AC 3.1.1, PS 3.9.2 | EVD-PS-03 |
| 7 | Are shared or generic accounts used anywhere in the environment? | Knowledge Check | AC 3.1.1 | EVD-AC-02 |
| 8 | How is remote access configured for field employees? What authentication is required? | Technical | AC 3.1.12, 3.1.13 | EVD-AC-04, EVD-AC-05 |
| 9 | Is MFA implemented? For which systems and users? | Technical | IA 3.5.3 | EVD-IA-02 |
| 10 | How do you manage mobile devices and BYOD? What controls are in place for personal phones accessing email and data? | Behavioral | AC 3.1.18, 3.1.19 | EVD-AC-07, EVD-AC-08 |
| 11 | Are USB ports restricted on workstations? How? | Technical | AC 3.1.20, MP 3.8.3 | EVD-AC-12 |

#### 3.3 Awareness & Training (AT)

| # | Question | Type | Controls Addressed | Cross-Reference |
|:-:|----------|:----:|:------------------:|:--------------:|
| 12 | What security awareness training do employees receive? How often? Is attendance tracked? | Behavioral | AT 3.2.1, 3.2.2 | EVD-AT-01, EVD-AT-02 |
| 13 | Do you provide specific CUI handling training to employees who work with government contracts? | Behavioral | AT 3.2.2 | EVD-AT-03 |

#### 3.4 Audit & Accountability (AU)

| # | Question | Type | Controls Addressed | Cross-Reference |
|:-:|----------|:----:|:------------------:|:--------------:|
| 14 | What systems are currently logging audit events? How long are logs retained? | Technical | AU 3.3.1 | EVD-AU-02 |
| 15 | How do you review logs? How often? Can you show me recent evidence of log review? | Behavioral | AU 3.3.3 | EVD-AU-04 |
| 16 | How would you know if logging stopped on a critical system? | Knowledge Check | AU 3.3.4 | EVD-AU-07 |

#### 3.5 Configuration Management (CM)

| # | Question | Type | Controls Addressed | Cross-Reference |
|:-:|----------|:----:|:------------------:|:--------------:|
| 17 | Do you have documented baseline configurations for workstations and servers? What standard do you use (CIS, STIG, other)? | Knowledge Check | CM 3.4.1, 3.4.2 | EVD-CM-01, EVD-CM-03 |
| 18 | Walk me through how you handle a typical system change — for example, installing a new software update on the server. | Process Walkthrough | CM 3.4.3, 3.4.4 | EVD-CM-05 |

#### 3.6 Incident Response (IR)

| # | Question | Type | Controls Addressed | Cross-Reference |
|:-:|----------|:----:|:------------------:|:--------------:|
| 19 | Do you have an Incident Response Plan? When was it last tested? | Knowledge Check | IR 3.6.1, 3.6.3 | EVD-IR-01, EVD-IR-04 |
| 20 | Walk me through what you would do if you discovered that a laptop with CUI was stolen from a construction site. | Process Walkthrough | IR 3.6.1, 3.6.2 | EVD-IR-02 |
| 21 | Are you aware of the DFARS 72-hour reporting requirement for cyber incidents involving CUI? | Knowledge Check | IR 3.6.2 | EVD-IR-03 |

#### 3.7 Maintenance (MA)

| # | Question | Type | Controls Addressed | Cross-Reference |
|:-:|----------|:----:|:------------------:|:--------------:|
| 22 | How do you manage patching? What is your typical patching cycle for critical vs. routine patches? | Behavioral | MA 3.7.1, SI 3.14.1 | EVD-MA-02 |

#### 3.8 Media Protection (MP)

| # | Question | Type | Controls Addressed | Cross-Reference |
|:-:|----------|:----:|:------------------:|:--------------:|
| 23 | Are laptops encrypted? What about the NAS? Backups? | Knowledge Check | MP 3.8.9, SC 3.13.14 | EVD-MP-03, EVD-SC-04 |
| 24 | What is your process for disposing of old hard drives or decommissioned equipment? | Behavioral | MP 3.8.5 | EVD-MP-04 |

#### 3.9 Risk Assessment (RA) & Security Assessment (CA)

| # | Question | Type | Controls Addressed | Cross-Reference |
|:-:|----------|:----:|:------------------:|:--------------:|
| 25 | Do you perform vulnerability scanning? What tools do you use? How often? | Technical | RA 3.11.2 | EVD-RA-03 |
| 26 | Do you have a System Security Plan (SSP)? If so, when was it last updated? | Knowledge Check | CA 3.12.4 | EVD-CA-01 |
| 27 | How do you continuously monitor security controls to ensure they remain effective? | Behavioral | CA 3.12.1, 3.12.3 | EVD-CA-03 |

#### 3.10 System & Communications Protection (SC)

| # | Question | Type | Controls Addressed | Cross-Reference |
|:-:|----------|:----:|:------------------:|:--------------:|
| 28 | Can you describe your network architecture — how is the network segmented? Where is the boundary? | Knowledge Check | SC 3.13.1, 3.13.5 | EVD-SC-01 |
| 29 | Is the guest Wi-Fi network isolated from the corporate network? | Technical | SC 3.13.5 | EVD-SC-07 |
| 30 | What encryption standards are you using for VPN, email, and cloud services? Are any of them FIPS-validated? | Technical | SC 3.13.8, 3.13.11 | EVD-SC-03, EVD-SC-05 |

#### 3.11 Managed Service Provider (MSP) Questions

| # | Question | Type | Controls Addressed | Cross-Reference |
|:-:|----------|:----:|:------------------:|:--------------:|
| 31 | What level of access does your MSP have to your systems? | Behavioral | AC 3.1.15, MA 3.7.2 | EVD-MA-03 |
| 32 | Does the MSP use MFA for remote access to your environment? | Knowledge Check | IA 3.5.3, MA 3.7.5 | EVD-MA-04 |
| 33 | What security requirements are in the MSP contract? Do you have oversight of their activities? | Behavioral | CA 3.12.4, MA 3.7.6 | EVD-MA-03, EVD-MA-05 |

---

### 4. Property Manager (Sample — Property Office A)

**Estimated Time:** 30 minutes
**Purpose:** Operational data handling, CUI awareness, day-to-day practices

| # | Question | Type | Controls Addressed | Cross-Reference |
|:-:|----------|:----:|:------------------:|:--------------:|
| 1 | Walk me through what happens when a new tenant moves in. What information do you collect? Where does it go? | Process Walkthrough | AC 3.1.3 | EVD-AC-01 |
| 2 | What systems do you use day-to-day? How do you log in? | Knowledge Check | IA 3.5.3 | EVD-IA-02 |
| 3 | Do you ever access these systems from home or on your phone? How? | Behavioral | AC 3.1.12, 3.1.18 | EVD-AC-04, EVD-AC-07 |
| 4 | Have you received security awareness training? What do you remember from it? | Knowledge Check | AT 3.2.1 | EVD-AT-02 |
| 5 | What would you do if you received an email asking you to wire money or share tenant passwords? | Behavioral | AT 3.2.1, SI 3.14.2 | EVD-AT-01 |
| 6 | Do you know what CUI is? Have you ever seen data marked as CUI? | Knowledge Check | AT 3.2.2 | EVD-AT-03 |
| 7 | How do you share tenant documents with other staff or external parties (e.g., maintenance contractors, corporate office)? | Behavioral | AC 3.1.3, SC 3.13.8 | — |
| 8 | What happens to paper documents containing tenant PII when you are finished with them? | Behavioral | MP 3.8.1 | EVD-MP-01 |
| 9 | Do you ever take files home on a USB drive or laptop? | Behavioral | MP 3.8.3 | EVD-MP-02 |
| 10 | Who would you report it to if you saw something suspicious — an unauthorized person in the office, a strange email, a coworker accessing files they shouldn't? | Behavioral | IR 3.6.1, AT 3.2.3 | EVD-IR-01 |

---

### 5. Construction Manager

**Estimated Time:** 20 minutes
**Purpose:** Field operations, remote access, data handling outside the office

| # | Question | Type | Controls Addressed | Cross-Reference |
|:-:|----------|:----:|:------------------:|:--------------:|
| 1 | Describe a typical day working between the office and construction sites. What IT equipment do you carry? | Process Walkthrough | — | Context |
| 2 | How do you access email, project files, and blueprints when you are at a construction site? | Behavioral | AC 3.1.12, 3.1.13 | EVD-AC-04, EVD-AC-05 |
| 3 | Do you ever save project files or blueprints locally on your laptop? Where are they stored? | Behavioral | SC 3.13.14 | EVD-SC-04 |
| 4 | Is your laptop encrypted? Do you lock it when you step away at a construction site? | Knowledge Check | AC 3.1.10, SC 3.13.14 | EVD-AC-09, EVD-SC-04 |
| 5 | Have you received any training about handling sensitive contract data? | Knowledge Check | AT 3.2.2 | EVD-AT-03 |
| 6 | What would you do if your laptop was lost or stolen? | Behavioral | IR 3.6.1, MP 3.8.5 | EVD-IR-01 |
| 7 | Do you share files with subcontractors? How? Email? USB? Cloud link? | Behavioral | AC 3.1.3 | — |
| 8 | Have you ever used personal email or a personal cloud service (Google Drive, Dropbox) to share work files? | Behavioral | SC 3.13.19 | EVD-AC-08 |

---

### 6. Finance / Admin Staff

**Estimated Time:** 20 minutes
**Purpose:** PII handling, financial data, HR records, termination process

| # | Question | Type | Controls Addressed | Cross-Reference |
|:-:|----------|:----:|:------------------:|:--------------:|
| 1 | What employee information do you handle? Where is it stored? | Knowledge Check | PS 3.9.1 | EVD-PS-01 |
| 2 | How is payroll data transmitted to the external payroll processor? | Behavioral | SC 3.13.8 | EVD-SC-03 |
| 3 | Walk me through the employee termination process from an IT and HR perspective. What happens to their accounts? | Process Walkthrough | PS 3.9.2 | EVD-PS-03 |
| 4 | Have you received security awareness training? Can you describe the key messages? | Knowledge Check | AT 3.2.1 | EVD-AT-02 |
| 5 | How do you share financial reports or sensitive information with the external accountant? | Behavioral | SC 3.13.8 | — |
| 6 | Are visitors to the office signed in and escorted? | Behavioral | PE 3.10.3 | EVD-PE-03 |

---

### 7. General Employee (Sample — Admin Assistant, Maintenance Coordinator, etc.)

**Estimated Time:** 15 minutes
**Purpose:** Baseline security awareness across the organization

| # | Question | Type | Controls Addressed | Cross-Reference |
|:-:|----------|:----:|:------------------:|:--------------:|
| 1 | Do you know how to create a strong password? What does the organization require? | Knowledge Check | IA 3.5.7 | EVD-IA-03 |
| 2 | Do you use MFA / two-step verification? For which systems? | Knowledge Check | IA 3.5.3 | EVD-IA-02 |
| 3 | What would you do if you received a suspicious email asking for your password or to click a link? | Behavioral | AT 3.2.1, SI 3.14.2 | EVD-AT-01 |
| 4 | Do you lock your computer when you step away from your desk? | Behavioral | AC 3.1.10 | EVD-AC-09 |
| 5 | Have you ever seen someone tailgate into the office (follow someone in without badging in)? What would you do? | Behavioral | PE 3.10.3 | EVD-PE-03 |
| 6 | Who would you report a security concern to? | Knowledge Check | IR 3.6.1 | EVD-IR-01 |

---

### 8. Process Walkthroughs

These are extended interview sessions where the interviewee demonstrates a process from start to finish while the assessor observes and asks clarifying questions.

| Walkthrough | Participants | Focus Controls |
|-------------|--------------|----------------|
| **Tenant Onboarding** | Property Manager | AC 3.1.2, 3.1.3, MP 3.8.1, SC 3.13.8 |
| **Employee Offboarding** | IT Manager + Admin | AC 3.1.1, PS 3.9.2, IA 3.5.6 |
| **Incident Response** | IT Manager | IR 3.6.1, 3.6.2, 3.6.3 |
| **Remote Access Setup** | IT Manager + Field Employee | AC 3.1.12, 3.1.13, IA 3.5.3 |
| **CUI Document Handling** | IT Manager + Admin | AC 3.1.3, MP 3.8.1, SC 3.13.14 |

---

### 9. Interview Schedule

| Week | Interviewee | Duration | Scheduled |
|:----:|-------------|:--------:|:---------:|
| 3 | Executive Sponsor | 30 min | |
| 3 | IT Manager (Part 1 — Policy & Access) | 60 min | |
| 3 | Property Manager A | 30 min | |
| 3 | Admin / Finance Representative | 20 min | |
| 4 | IT Manager (Part 2 — Technical) | 60 min | |
| 4 | Property Manager B | 30 min | |
| 4 | Construction Manager | 20 min | |
| 4 | General Employee Sample (2-3) | 15 min each | |
| 4 | Process Walkthroughs (as needed) | 30 min each | |

---

### 10. Interview Documentation Template

| Field | Value |
|-------|-------|
| **Interview ID** | INT-001 |
| **Date** | |
| **Time** | |
| **Interviewee Role** | |
| **Assessor** | |
| **Location** | |
| **Questions Asked** | (list Q numbers) |
| **Key Responses** | |
| **Policy vs. Practice Gaps Identified** | |
| **Evidence Obtained** | (EVD IDs) |
| **Controls Addressed** | |
| **Assessor Notes** | |

---

*Document Version: 1.0*
*Date: July 13, 2026*
