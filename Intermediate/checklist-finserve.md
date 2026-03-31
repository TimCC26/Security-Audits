# Controls and Compliance Checklist
## FinServe Credit Union

> **Difficulty:** Intermediate | **Industry:** Financial Services | **Frameworks:** PCI DSS v4.0, GLBA Safeguards Rule, NCUA, SOC 2
>
> Complete this checklist using the [FinServe Risk Assessment Report](./Intermediate/finserve.md) as reference.
>
> *Does FinServe Credit Union currently have this control in place?*

---

## Part 1 — Controls Assessment

### Administrative Controls

| Yes | No | Control | Notes |
|---|---|---|---|
| [ ] | [ ] | Least privilege / role-based access control | 18 Domain Admin accounts identified; only 4 require that level |
| [ ] | [ ] | Separation of duties | Not assessed for key financial workflows |
| [ ] | [ ] | Privileged access management (PAM) program | No formal PAM process; over-provisioning is widespread |
| [ ] | [ ] | Patch management program with enforced SLAs | Critical CVE (CVSS 8.8) open for 47 days, exceeding 30-day SLA |
| [ ] | [ ] | Third-party / vendor risk management with risk tiering | All vendors receive same questionnaire regardless of data access level |
| [ ] | [ ] | Acceptable Use Policy (current — covers cloud and remote work) | Last updated in 2021; does not address cloud services or remote work |
| [ ] | [ ] | Incident response plan | Plan exists but has not been tested via tabletop exercise |
| [ ] | [ ] | Disaster recovery plan (tested) | Not confirmed |
| [ ] | [ ] | Security awareness training program | Not confirmed |

### Technical Controls

| Yes | No | Control | Notes |
|---|---|---|---|
| [ ] | [ ] | Multi-factor authentication (MFA) enforced for all remote access | 23% of remote VPN sessions in past 90 days did not use MFA |
| [ ] | [ ] | SIEM with coverage across all in-scope systems | Splunk deployed but online banking application logs not ingested |
| [ ] | [ ] | SIEM alert tuning reviewed within past 12 months | Alert tuning has not been reviewed in 12 months |
| [ ] | [ ] | Firewall ruleset reviewed within past 12 months | Last reviewed 24 months ago; 12 rules flagged as potentially stale |
| [ ] | [ ] | Intrusion detection / prevention system (IDS/IPS) | Not confirmed |
| [ ] | [ ] | Vulnerability scanning program (web applications included) | Vendor scan conducted; findings not remediated within SLA |
| [ ] | [ ] | Penetration testing of mobile banking app within past 12 months | Last tested 18 months ago |
| [ ] | [ ] | Encryption of cardholder data at rest and in transit | Card numbers logged outside the CDE in plaintext application logs |
| [ ] | [ ] | Endpoint protection / antivirus on all workstations | Not confirmed for all 200+ workstations |
| [ ] | [ ] | Backups (tested) | Not confirmed |

### Physical Controls

| Yes | No | Control | Notes |
|---|---|---|---|
| [ ] | [ ] | Badge access controls at branch locations | In place and functional |
| [ ] | [ ] | CCTV surveillance at branch locations | In place and functional |
| [ ] | [ ] | Physical security at co-location data center | Managed by co-location provider; not independently verified |
| [ ] | [ ] | ATM physical tamper detection | Managed by ATM vendor; not assessed |

---

## Part 2 — Compliance Checklist

### Payment Card Industry Data Security Standard (PCI DSS v4.0)

*Does FinServe Credit Union currently adhere to this compliance best practice?*

| Yes | No | Best Practice |
|---|---|---|
| [ ] | [ ] | Cardholder data is not stored beyond business need; card numbers are not written to application logs. *(Req. 3.3)* |
| [ ] | [ ] | The cardholder data environment (CDE) is correctly scoped and isolated from other systems. |
| [ ] | [ ] | Only authorized users have access to cardholder data. |
| [ ] | [ ] | Cardholder data is encrypted at rest and in transit. |
| [ ] | [ ] | Vulnerability scans and penetration tests are conducted per PCI DSS schedule (quarterly scans, annual pen test). |
| [ ] | [ ] | Firewall rules protecting the CDE are reviewed at least every six months. |
| [ ] | [ ] | Strong authentication (MFA) is enforced for all access into the CDE. |

### Gramm-Leach-Bliley Act (GLBA) — Safeguards Rule

| Yes | No | Best Practice |
|---|---|---|
| [ ] | [ ] | A written Information Security Program (WISP) is in place and reviewed annually. |
| [ ] | [ ] | A qualified individual is designated to oversee the information security program (CISO or equivalent). |
| [ ] | [ ] | Risk assessments are conducted regularly with documented findings, assigned owners, and tracked remediation. |
| [ ] | [ ] | Service provider oversight is in place; contracts include security requirements and annual reviews. |
| [ ] | [ ] | An incident response plan addresses GLBA notification obligations. |
| [ ] | [ ] | Continuous monitoring of systems is implemented. |

### NCUA Cybersecurity Guidance

| Yes | No | Best Practice |
|---|---|---|
| [ ] | [ ] | The board of directors receives regular cybersecurity briefings. |
| [ ] | [ ] | Cybersecurity risk is integrated into the enterprise risk management (ERM) framework. |
| [ ] | [ ] | Technology service providers (TSSPs) are assessed for cybersecurity risk before and during engagement. |
| [ ] | [ ] | The credit union participates in sector information sharing (e.g., FS-ISAC). |
| [ ] | [ ] | The incident response plan covers member notification obligations. |

### System and Organizations Controls (SOC 2 — Trust Service Criteria)

| Yes | No | Best Practice |
|---|---|---|
| [ ] | [ ] | User access policies are established, enforced, and reviewed regularly. |
| [ ] | [ ] | Sensitive member data (PII/NPPI) is kept confidential. |
| [ ] | [ ] | Data integrity controls ensure member information is accurate and complete. |
| [ ] | [ ] | Systems are available to authorized members and staff per agreed service levels. |
| [ ] | [ ] | SOC 2 reports for key vendors (e.g., core banking platform) have been reviewed within the past 12 months. |

---

## Part 3 — Recommendations *(optional)*

*Based on the risk assessment findings, which controls and compliance gaps pose the greatest risk to FinServe if not addressed promptly? Consider regulatory examination exposure, member data liability, and the open CVE when prioritizing.*

**Your notes:**

>

---

*This scenario is a fictional practice exercise for cybersecurity audit and controls assessment training.*
