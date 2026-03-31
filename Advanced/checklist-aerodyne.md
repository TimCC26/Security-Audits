# Controls and Compliance Checklist
## AeroDyne Systems Inc.

> **Difficulty:** Advanced | **Industry:** Defense / Aerospace | **Frameworks:** CMMC Level 2, NIST SP 800-171 Rev. 2, DFARS, MITRE ATT&CK
>
> Complete this checklist using the [AeroDyne Risk Assessment Report](./Advanced/aerodyne.md) as reference.
>

---

## Part 1 — Controls Assessment (CUI Boundary)

*Does AeroDyne Systems currently have this control in place within the CUI boundary?*

### Administrative Controls

| Yes | No | Control | Notes |
|---|---|---|---|
| [ ] | [ ] | Least privilege enforced for all CUI-access accounts | Shared accounts exist on CNC machines in the MES environment |
| [ ] | [ ] | Separation of duties (IT admin, system owner, end user) | Not confirmed for MES environment |
| [ ] | [ ] | System Security Plan (SSP) complete and current for all CUI boundaries | SSP incomplete for the MES system boundary |
| [ ] | [ ] | Plan of Action & Milestones (POA&M) with assigned owners and closure dates | POA&M items exist but lack closure dates |
| [ ] | [ ] | Supply chain risk management — SPRS scores obtained from all CUI-handling subcontractors | 0 of 9 CUI subcontractors have provided current SPRS scores |
| [ ] | [ ] | Security awareness and role-based CUI training completed annually | Annual training completed; role-based CUI training deployed |
| [ ] | [ ] | Personnel security — background checks enforced for CUI access | Background checks enforced |
| [ ] | [ ] | CUI access revoked within 24 hours of employee separation | Process confirmed |
| [ ] | [ ] | Configuration baselines approved and enforced for all CUI systems | No approved baseline for CNC-connected workstations; 3 open CCBs |
| [ ] | [ ] | Remote maintenance sessions for vendors (e.g., MES vendor) are logged and supervised | MES vendor remote sessions are not logged or supervised |
| [ ] | [ ] | Incident response plan tested (includes CUI breach and DIBNet reporting procedures) | IR plan exists; red team revealed lateral movement detection gap |
| [ ] | [ ] | Disaster recovery / COOP plan tested within past 12 months | Last full restore test was 14 months ago |

### Technical Controls

| Yes | No | Control | Notes |
|---|---|---|---|
| [ ] | [ ] | MFA enforced for all accounts with CUI access, including service accounts | MFA not enforced for 6 service accounts with CUI access |
| [ ] | [ ] | Privileged Access Workstations (PAWs) enforced for all administrative activity | 11% of MES-connected endpoints lack PAW enforcement |
| [ ] | [ ] | EDR (CrowdStrike Falcon) deployed on 100% of CUI-boundary endpoints | 11% coverage gap on legacy MES-connected workstations |
| [ ] | [ ] | SIEM (Sentinel) ingests logs from all CUI systems, including MES | MES logs are not currently ingested into Sentinel |
| [ ] | [ ] | Detection rules exist for lateral movement (DCOM, WMI, PowerShell abuse) | Red team confirmed no alerts triggered during lateral movement via DCOM |
| [ ] | [ ] | DCOM blocked from enabling lateral movement between IT and OT/MES networks | DCOM unmonitored and unrestricted — exploited in Q1 red team exercise |
| [ ] | [ ] | CUI encrypted in transit between MES and EDN VLAN | CUI is not encrypted in transit between these segments |
| [ ] | [ ] | CUI encrypted at rest on EDN workstations and servers | Not confirmed for all 320 workstations and 45 servers |
| [ ] | [ ] | Data Loss Prevention (DLP) solution deployed | No DLP solution deployed |
| [ ] | [ ] | USB / removable media restricted on all EDN workstations | USB ports unrestricted on 28 EDN workstations |
| [ ] | [ ] | Audit logs retained for minimum 90 days across all CUI systems | Log retention < 90 days on 2 systems |
| [ ] | [ ] | File integrity monitoring (FIM) on MES systems | No FIM deployed on MES |
| [ ] | [ ] | Vulnerability management / patch management SLA enforced | Not confirmed for MES-connected legacy systems |

### Physical Controls

| Yes | No | Control | Notes |
|---|---|---|---|
| [ ] | [ ] | Badge access enforced at all CUI workspace entry points | In place; however, tailgating observed at West Wing entry |
| [ ] | [ ] | Visitor escort log maintained for CUI workspace areas | No visitor escort log in place |
| [ ] | [ ] | Anti-tailgating controls at West Wing entry point | Tailgating has been directly observed |
| [ ] | [ ] | Physical media (drives, printouts) containing CUI is tracked and disposed of securely | Not confirmed |

---

## Part 2 — Compliance Checklist

### NIST SP 800-171 Rev. 2 — All 14 Control Families

*Does AeroDyne Systems currently meet the requirements of each control family?*

| Yes | No | Control Family | Key Requirement from Scenario |
|---|---|---|---|
| [ ] | [ ] | **3.1 Access Control** | Eliminate shared CNC accounts; enforce PAW on 100% of MES endpoints |
| [ ] | [ ] | **3.2 Awareness & Training** | Annual and role-based CUI training — currently implemented |
| [ ] | [ ] | **3.3 Audit & Accountability** | Ingest MES logs into Sentinel; fix log retention gaps on 2 systems |
| [ ] | [ ] | **3.4 Configuration Management** | Establish and enforce approved baselines for CNC-connected workstations; resolve 3 open CCBs |
| [ ] | [ ] | **3.5 Identification & Authentication** | Enforce MFA on all 6 service accounts with CUI access |
| [ ] | [ ] | **3.6 Incident Response** | Update IR plan to address lateral movement detection gaps revealed by red team |
| [ ] | [ ] | **3.7 Maintenance** | Log and supervise all remote maintenance sessions for MES vendor |
| [ ] | [ ] | **3.8 Media Protection** | Deploy DLP; restrict USB on all 28 affected EDN workstations |
| [ ] | [ ] | **3.9 Personnel Security** | Background checks enforced; separation process confirmed — currently implemented |
| [ ] | [ ] | **3.10 Physical Protection** | Implement anti-tailgating at West Wing; establish visitor escort log |
| [ ] | [ ] | **3.11 Risk Assessment** | Complete supply chain risk assessment for all 9 CUI-handling subcontractors |
| [ ] | [ ] | **3.12 Security Assessment** | Complete SSP for MES boundary; assign owners and closure dates to all POA&M items |
| [ ] | [ ] | **3.13 System & Comm. Protection** | Block DCOM lateral movement; encrypt CUI in transit between MES and EDN VLAN |
| [ ] | [ ] | **3.14 System & Info. Integrity** | Extend EDR to remaining 11% of endpoints; deploy FIM on MES |

### CMMC Level 2 — Process Requirements

| Yes | No | Best Practice |
|---|---|---|
| [ ] | [ ] | All 110 NIST SP 800-171 practices are documented in the SSP. |
| [ ] | [ ] | POA&M items are tracked with milestones, assigned owners, and estimated completion dates. |
| [ ] | [ ] | The SPRS score has been self-assessed, documented, and submitted to the SPRS portal. |
| [ ] | [ ] | A C3PAO assessment has been scheduled (required ahead of Q3 target). |
| [ ] | [ ] | All CUI-handling subcontractors are contractually required to meet CMMC Level 2. |
| [ ] | [ ] | DFARS clause 252.204-7021 flow-down requirements are included in all relevant subcontracts. |

### DFARS / Regulatory Obligations

| Yes | No | Best Practice |
|---|---|---|
| [ ] | [ ] | Cyber incidents are reported to DoD via DIBNet within 72 hours of discovery. |
| [ ] | [ ] | Malicious software discovered during incident response is submitted to DC3 (DoD Cyber Crime Center). |
| [ ] | [ ] | ITAR-controlled CAD data is segregated on the air-gapped EDN segment; access limited to U.S. persons only. |
| [ ] | [ ] | CUI is marked and handled per the CUI Registry and applicable DoD agency guidance. |

### Threat Coverage — MITRE ATT&CK

*Is a detective or preventive control in place for each confirmed or probable TTP?*

| Yes | No | Technique | Threat | Current Gap |
|---|---|---|---|---|
| [ ] | [ ] | T1566.001 — Spearphishing Attachment | APT40 | No specific detection rules for malicious DXF/STEP attachments |
| [ ] | [ ] | T1078 — Valid Accounts | APT40 / APT29 | MFA not enforced on all accounts; credential stuffing risk on VPN |
| [ ] | [ ] | T1021.003 — DCOM Lateral Movement | APT29 | DCOM unrestricted; **confirmed exploited in Q1 red team exercise** |
| [ ] | [ ] | T1059.001 — PowerShell / WMIC (LotL) | APT29 | No detection rules in Sentinel for living-off-the-land techniques |
| [ ] | [ ] | T1195 — Supply Chain Compromise | APT40 | 2 of 9 CUI subcontractors have not responded to security questionnaires |

---

## Part 3 — SPRS Score Tracker *(optional)*

*Use this section to calculate AeroDyne's projected SPRS score after remediating identified POA&M items.*

| Metric | Value |
|---|---|
| Maximum possible score | +110 |
| Current self-assessed score | +47 |
| Points lost to open POA&M items (from report) | -30 |
| Projected score if all POA&M items remediated | +77 |
| Additional gap to reach +110 | -33 |

> 💡 **Note:** The POA&M items in the report account for -30 points. Reaching a full score of +110 will require addressing the remaining unscored gaps (e.g., FIM on MES, full DLP deployment, and supply chain questionnaire completion).

---

## Part 4 — Recommendations *(optional)*

*Based on the risk assessment and SPRS score analysis, which POA&M items should be prioritized to reduce contractual risk and improve the security posture of AeroDyne's CUI environment before the C3PAO assessment? Consider the red team findings, open subcontractor gaps, and DFARS obligations in your response.*

**Your notes:**

>

---

*This scenario is a fictional practice exercise for cybersecurity audit and controls assessment training.*
