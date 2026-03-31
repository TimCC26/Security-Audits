# Controls and Compliance Checklist
## MediQuick Urgent Care

> **Difficulty:** Beginner | **Industry:** Healthcare | **Frameworks:** HIPAA Security Rule, NIST CSF
>
> Complete this checklist using the [MediQuick Risk Assessment Report](./mediquick.md) as reference.
>
> *Does MediQuick Urgent Care currently have this control in place?*

---

## Part 1 — Controls Assessment

### Administrative Controls

| Yes | No | Control | Notes |
|---|---|---|---|
| [ ] | [ ] | Documented security policies and procedures | No formal policies exist |
| [ ] | [ ] | Separation of duties | IT coordinator holds full admin access to all systems |
| [ ] | [ ] | Least privilege access | All staff have equal access; no role-based permissions |
| [ ] | [ ] | Security awareness training for all staff | Staff have received no security training |
| [ ] | [ ] | Business Associate Agreement (BAA) with EHR vendor | Vendor contract has not been reviewed for BAA compliance |
| [ ] | [ ] | Asset inventory with assigned ownership | No documented inventory exists |
| [ ] | [ ] | Password policy | No password policy is in place |

### Technical Controls

| Yes | No | Control | Notes |
|---|---|---|---|
| [ ] | [ ] | Multi-factor authentication (MFA) | Not enabled on any account, including the EHR portal |
| [ ] | [ ] | Unique Wi-Fi credentials per location (not shared) | Single shared Wi-Fi password across all 3 locations; never changed |
| [ ] | [ ] | Encryption of PHI at rest | Patient intake PDFs stored unencrypted in Google Drive |
| [ ] | [ ] | Encryption of PHI in transit (ePHI) | Not confirmed for EHR vendor communications |
| [ ] | [ ] | Access controls on shared cloud storage | Google Drive folder is accessible to all staff with no restrictions |
| [ ] | [ ] | Antivirus / endpoint protection on workstations | Not confirmed on Windows 10 check-in computers |
| [ ] | [ ] | Firewall on clinic network | Consumer-grade routers with no managed firewall configuration |
| [ ] | [ ] | Backups of clinic data | No backup plan documented; data is on-device or in Google Drive |
| [ ] | [ ] | Audit logging / access tracking for EHR | Not confirmed; depends on EHR vendor configuration |
| [ ] | [ ] | Password management system | No password manager in use |

### Physical Controls

| Yes | No | Control | Notes |
|---|---|---|---|
| [ ] | [ ] | Restricted access to server closet / network equipment | Server closet is shared with supply room; unrestricted access |
| [ ] | [ ] | Locks on exam rooms containing patient data | Not assessed |
| [ ] | [ ] | CCTV surveillance at clinic locations | Not confirmed |
| [ ] | [ ] | Fire detection / prevention systems | Not confirmed |

---

## Part 2 — Compliance Checklist

### Health Insurance Portability and Accountability Act (HIPAA) — Security Rule

*Does MediQuick Urgent Care currently adhere to this compliance best practice?*

| Yes | No | Best Practice |
|---|---|---|
| [ ] | [ ] | A Security Risk Analysis (SRA) has been completed and documented. |
| [ ] | [ ] | Only authorized workforce members have access to PHI. |
| [ ] | [ ] | ePHI transmitted to/from the EHR vendor is encrypted in transit. |
| [ ] | [ ] | PHI stored in Google Drive or on-device is encrypted at rest. |
| [ ] | [ ] | A Business Associate Agreement (BAA) is in place with the EHR vendor. |
| [ ] | [ ] | Workforce members receive annual HIPAA security awareness training. |
| [ ] | [ ] | Audit controls track who accesses PHI and when. |
| [ ] | [ ] | A Breach Notification Policy exists that meets the 60-day HHS notification requirement. |
| [ ] | [ ] | Unique user credentials are used for EHR access (no shared logins). |

### NIST Cybersecurity Framework (CSF) — Core Functions

| Yes | No | Best Practice |
|---|---|---|
| [ ] | [ ] | **Identify:** All assets that store, process, or transmit PHI are inventoried and assigned an owner. |
| [ ] | [ ] | **Protect:** Access to PHI systems is restricted to minimum necessary staff. |
| [ ] | [ ] | **Protect:** Security policies and procedures are documented and reviewed at least annually. |
| [ ] | [ ] | **Protect:** Staff receive regular security awareness training. |
| [ ] | [ ] | **Detect:** Processes exist to identify unauthorized access to PHI or clinic systems. |
| [ ] | [ ] | **Respond:** An incident response plan is documented and staff know their roles. |
| [ ] | [ ] | **Recover:** A data backup and recovery plan exists and has been tested. |

---

## Part 3 — Recommendations *(optional)*

*Based on the risk assessment findings, which controls and compliance gaps pose the greatest risk to MediQuick if not addressed promptly? Consider the potential for HIPAA violations, PHI exposure, and patient trust when prioritizing your recommendations.*

**Your notes:**

>

---

*This scenario is a fictional practice exercise for cybersecurity audit and controls assessment training.*
