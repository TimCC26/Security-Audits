# FinServe Credit Union
## Scope, Goals, and Risk Assessment Report

> **Difficulty:** Intermediate | **Industry:** Financial Services | **Size:** Medium (2 branches, ~200 staff)

---

## Scope and Goals of the Audit

### Scope

This audit covers the full security program at FinServe Credit Union, including its two branch locations, a central data center hosted at a co-location facility, and all digital member-facing services (online banking portal, mobile app). Third-party integrations with the ACH network, core banking vendor, and ATM management system are in scope. Human Resources and Marketing IT systems are out of scope for this engagement.

### Goals

Evaluate FinServe's current controls against **PCI DSS v4.0**, **GLBA Safeguards Rule**, and **NCUA cybersecurity guidance**. Identify gaps in technical, administrative, and physical controls and produce a prioritized remediation roadmap. Confirm the credit union's ability to detect, contain, and recover from a cyber incident.

---

## Current Assets

Assets within audit scope include:

- Core banking platform (hosted by third-party vendor, FiServe360) accessed via dedicated MPLS link
- Online banking portal: web application on AWS, managed by an internal development team of 3
- Mobile banking app (iOS and Android): version 4.2, last penetration tested 18 months ago
- ATM fleet: 8 ATMs across 2 branches, managed via ATM vendor network
- 200+ Windows 10/11 employee workstations; Active Directory environment
- On-premises VMware cluster (8 hosts) running internal applications and file shares
- Cisco ASA firewalls at both branches and co-location; last rule review was 2 years ago
- SIEM platform (Splunk): deployed but alert tuning has not been reviewed in 12 months
- Hardware security tokens for remote VPN access (not enforced for all staff)
- Member card data processed via a PCI-compliant third-party processor; however, some card numbers are logged in internal systems

---

## Risk Assessment

### Risk Description

FinServe operates in a highly regulated environment and is subject to NCUA examination. The credit union has a dedicated IT team of 6 and a part-time CISO. While several foundational controls exist, a recent internal review flagged inconsistencies in patch management, overprivileged accounts, and insufficient monitoring coverage on the online banking platform. An unpatched vulnerability in the web application framework (CVE-2024-XXXX, CVSS 8.8) was identified during a recent vendor scan and has not yet been remediated.

### Control Best Practices

The NIST CSF **Detect** and **Respond** functions are the priority improvement areas. FinServe's SIEM coverage does not include the online banking platform logs, meaning anomalous transactions could go undetected. The **Protect** function requires attention for privileged access management and third-party risk management, both of which are under-documented.

### Risk Score

| Risk Area | Score (1–10) | Severity | Justification |
|---|---|---|---|
| **Overall Risk Score** | **8** | 🔴 HIGH | Unpatched web app CVE + insufficient detection coverage |
| PCI DSS Compliance | 7 | 🔴 HIGH | Card numbers logged in internal system outside CDE scope |
| Third-Party Risk | 6 | 🟡 MEDIUM | Core banking vendor SOC 2 report not reviewed in 24 months |
| Incident Response Readiness | 5 | 🟡 MEDIUM | IR plan exists but has not been tested via tabletop exercise |
| Physical Security | 3 | 🟢 LOW | Badge access and CCTV are in place and functional |

### Additional Comments — Detailed Findings

**Technical Controls:**

- 🔴 **CRITICAL:** An unpatched critical vulnerability (CVSS 8.8) in the online banking web framework has been open for 47 days, exceeding the credit union's own 30-day SLA for critical patches.
- SIEM alerting does not ingest online banking application logs; a threat actor conducting low-and-slow account takeover activity would not be detected.
- Firewall rules have not been reviewed in 24 months; 12 rules have been identified as potentially redundant or overly permissive.
- VPN hardware tokens are issued to all remote employees, but enforcement is inconsistent — 23% of remote sessions in the past 90 days did not use MFA.

**Administrative Controls:**

- 18 accounts with Domain Administrator privileges have been identified; only 4 administrators require this level of access.
- The third-party vendor management program lacks a formal risk tiering methodology; all vendors receive the same annual questionnaire regardless of data access level.
- The Acceptable Use Policy was last updated in 2021 and does not address cloud services or remote work.

**Compliance Controls:**

- Card numbers from declined transactions are being written to an application log stored outside the cardholder data environment (CDE), which violates **PCI DSS Requirement 3.3**.
- GLBA annual risk assessment was completed, but remediation tracking is informal and lacks assigned ownership and due dates.

---

*This scenario is a fictional practice exercise for cybersecurity audit and controls assessment training.*
