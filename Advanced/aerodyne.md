# AeroDyne Systems Inc.
## Scope, Goals, and Risk Assessment Report

> **Difficulty:** Advanced | **Industry:** Defense / Aerospace | **Size:** Large (~1,200 staff)
>

---

## Scope and Goals of the Audit

### Scope

This audit covers AeroDyne Systems' entire cybersecurity program as it pertains to the handling of **Controlled Unclassified Information (CUI)** and **Federal Contract Information (FCI)**. In scope: the Engineering Design Network (EDN), Secure Collaboration Platform (SCP), Manufacturing Execution System (MES), and all endpoints connecting to these environments. Cloud workloads in Azure GovCloud are in scope. Consumer-facing marketing and recruitment systems are explicitly out of scope.

This assessment is conducted in preparation for a **Cybersecurity Maturity Model Certification (CMMC) Level 2** assessment, as required under DFARS clause 252.204-7021. All 110 practices mapped to **NIST SP 800-171 Rev. 2** are subject to evaluation.

### Goals

- Complete a System Security Plan (SSP) gap analysis against all 14 control families of NIST SP 800-171 Rev. 2
- Identify and score all Plan of Action & Milestones (POA&M) items with SPRS score implications
- Assess supply chain risk for all Tier 1 and Tier 2 subcontractors processing CUI on behalf of AeroDyne
- Evaluate AeroDyne's ability to detect, respond to, and recover from an Advanced Persistent Threat (APT) actor consistent with nation-state TTPs targeting the defense industrial base (DIB)
- Provide an updated SPRS score and prioritized remediation roadmap ahead of the scheduled C3PAO assessment in Q3

---

## Current Assets — CUI Environment

The following assets are within the CUI boundary and subject to NIST 800-171 controls:

- **Engineering Design Network (EDN):** 320 Windows 11 workstations, 45 RHEL 8 servers; air-gapped segment for ITAR-controlled CAD data
- **Secure Collaboration Platform (SCP):** SharePoint Online (GCC High tenant) and Microsoft Teams GCC High for CUI collaboration
- **Manufacturing Execution System (MES):** Siemens Opcenter on-premises, connected to EDN via VLAN; interfaces with 12 CNC machines and 4 3D printing systems
- **Identity platform:** Azure AD (Entra ID) for GCC High; on-premises Active Directory for EDN; Privileged Access Workstations (PAWs) for admin activities
- **EDR:** CrowdStrike Falcon deployed on 89% of endpoints; 11% coverage gap on legacy MES-connected workstations
- **SIEM:** Microsoft Sentinel; log collection covers EDN, SCP, and Azure GovCloud; MES logs are not currently ingested
- **Backup:** Veeam on-premises for EDN; Azure Backup for GCC High; last full restore test was 14 months ago
- **Physical:** CUI workspaces are badge-restricted; tailgating has been observed at the West Wing entry point
- **Supply chain:** 38 active subcontractors; 9 handle CUI directly; none have provided current SPRS scores

---

## Risk Assessment

### Risk Description

AeroDyne operates as a prime contractor and subcontractor across 4 active DoD programs. Recent threat intelligence from CISA and DIBNet indicates elevated targeting of aerospace manufacturers by **APT40** (PRC-nexus) and **APT29** (Russia-nexus) actors using spearphishing and VPN exploitation techniques.

AeroDyne's self-assessed **SPRS score is currently +47**, which is below the DoD's informal threshold and represents a contractual risk if not improved prior to the C3PAO assessment.

A recent red team exercise (conducted by an external firm in Q1) successfully achieved **lateral movement from a compromised engineering workstation to the MES network within 4 hours**, without triggering any SIEM alerts. The exercise identified an unmonitored legacy protocol (DCOM) enabling east-west movement.

### Risk Score — NIST 800-171 Control Family Summary

| Control Family | Practices | Status | Key Gap / Finding |
|---|---|---|---|
| 3.1 Access Control | 22 | 🟡 PARTIAL | 11% of MES endpoints lack PAW enforcement; shared accounts on CNC machines |
| 3.2 Awareness & Training | 3 | 🟢 IMPLEMENTED | Annual training completed; role-based CUI training deployed |
| 3.3 Audit & Accountability | 9 | 🟡 PARTIAL | MES audit logs not forwarded to SIEM; log retention < 90 days on 2 systems |
| 3.4 Configuration Management | 9 | 🟡 PARTIAL | No approved baseline config for CNC-connected workstations; 3 open CCBs |
| 3.5 Identification & Authentication | 11 | 🟡 PARTIAL | MFA not enforced for 6 service accounts with CUI access |
| 3.6 Incident Response | 3 | 🟡 PARTIAL | IR plan exists; red team exercise revealed detection gap on lateral movement |
| 3.7 Maintenance | 6 | 🔴 NOT MET | Remote maintenance sessions for MES vendor not logged or supervised |
| 3.8 Media Protection | 9 | 🟡 PARTIAL | USB ports unrestricted on 28 EDN workstations; no DLP solution deployed |
| 3.9 Personnel Security | 2 | 🟢 IMPLEMENTED | Background checks enforced; CUI access removed within 24hr of separation |
| 3.10 Physical Protection | 6 | 🟡 PARTIAL | Tailgating at West Wing entry; no visitor escort log for CUI workspace |
| 3.11 Risk Assessment | 3 | 🟡 PARTIAL | Annual risk assessment conducted; supply chain risk assessment not completed |
| 3.12 Security Assessment | 4 | 🟡 PARTIAL | SSP incomplete for MES boundary; POA&M items lack closure dates |
| 3.13 System & Comm. Protection | 16 | 🔴 NOT MET | DCOM not blocked; CUI not encrypted in transit between MES and EDN VLAN |
| 3.14 System & Info. Integrity | 7 | 🟡 PARTIAL | EDR not deployed on 11% of endpoints; no file integrity monitoring on MES |

### SPRS Score Impact Analysis

> Current SPRS Score: **+47** | Target: **+110**

| POA&M Item | SPRS Points | Remediation Effort | Timeline |
|---|---|---|---|
| Implement MFA on all CUI-access service accounts (3.5.3) | -5 | 🟢 Low | 30 days |
| Log and supervise all remote MES vendor maintenance sessions (3.7.5) | -5 | 🟢 Low | 30 days |
| Obtain SPRS scores from 9 CUI-handling subcontractors (3.11.1) | -1 | 🟢 Low | 45 days |
| Ingest MES logs into Sentinel; create lateral movement detection rules (3.3.1, 3.3.2) | -3 | 🟡 Medium | 60 days |
| Block DCOM laterally; encrypt CUI in transit between MES and EDN (3.13.8) | -5 | 🟡 Medium | 60 days |
| Deploy DLP and restrict USB on all EDN endpoints (3.8.1) | -3 | 🟡 Medium | 90 days |
| Extend EDR coverage to remaining 11% of endpoints (3.14.2) | -5 | 🟡 Medium | 60 days |
| Complete SSP for MES boundary; close all open POA&M items (3.12.1) | -3 | 🔴 High | 90 days |

### Threat Context — Defense Industrial Base

Current DIB threat intelligence warrants priority attention to the following TTPs:

| MITRE Technique | Description | Threat Actor |
|---|---|---|
| T1566.001 | Spearphishing with weaponized engineering file attachments (malicious DXF/STEP files) targeting CAD operators | APT40 |
| T1078 | Valid account abuse via credential stuffing on VPN portals — observed at 3 peer DIB companies in past 6 months | APT40 / APT29 |
| T1021.003 | Lateral movement via legacy protocols (DCOM, WMI) from IT to OT/MES environments — **confirmed in Q1 red team exercise** | APT29 |
| T1059.001 | Living-off-the-land via PowerShell and WMIC to evade EDR — would not trigger current Sentinel detection rules | APT29 |
| T1195 | Supply chain compromise via subcontractor with direct CUI system access — 2 of 9 CUI subcontractors have not responded to questionnaires | APT40 |

---

*This scenario is a fictional practice exercise for cybersecurity audit and controls assessment training.*
