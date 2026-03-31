# MediQuick Urgent Care
## Scope, Goals, and Risk Assessment Report

> **Difficulty:** Beginner | **Industry:** Healthcare | **Size:** Small (3 locations, ~30 staff)

---

## Scope and Goals of the Audit

### Scope

This audit covers MediQuick Urgent Care's entire IT and security environment, including patient check-in systems, staff workstations, and the clinic's internal Wi-Fi network. All three locations (downtown, east side, and airport) are in scope.

### Goals

Assess existing assets and complete the controls and compliance checklist to determine which controls and compliance best practices need to be implemented to improve MediQuick's security posture and ensure HIPAA compliance.

---

## Current Assets

Assets managed by the IT coordinator include:

- 5 front-desk check-in computers (Windows 10) at each of the 3 locations
- 1 shared staff scheduling tablet per location
- Electronic Health Record (EHR) software hosted by a third-party vendor
- Wi-Fi routers at each location (consumer-grade, not managed)
- A single shared Google Drive folder used to store patient intake forms
- 1 laser printer per location, networked
- No dedicated server — all files stored in Google Drive or on-device

---

## Risk Assessment

### Risk Description

MediQuick's IT environment is managed by a single part-time IT coordinator with limited formal security training. There are no documented security policies, and staff use personal email accounts to communicate about patient scheduling. The clinic stores some patient intake forms in an unprotected shared Google Drive folder accessible to all staff.

### Control Best Practices

Using the NIST CSF **Identify** function as a starting point, MediQuick must document all assets and assign ownership. The **Protect** function highlights the need for access controls and encryption. Because the clinic handles Protected Health Information (PHI), HIPAA Security Rule compliance is a legal obligation, not optional.

### Risk Score

| Risk Area | Score (1–10) | Justification |
|---|---|---|
| **Overall Risk Score** | **7** | Moderate risk due to PHI exposure and lack of formal policies |
| Regulatory / Compliance Risk | 8 | HIPAA violations could result in fines and reputational damage |
| Data Loss Risk | 5 | No backups, but data is cloud-hosted by EHR vendor |

### Additional Comments

Key vulnerabilities identified during the preliminary review:

- All staff share a single Wi-Fi password that has never been changed.
- Patient intake PDFs containing names and dates of birth are stored in an unsecured shared Google Drive with no expiry or permission review.
- No multi-factor authentication (MFA) is enabled on any account, including the EHR portal.
- The IT coordinator has full administrator access to all systems; there is no separation of duties.
- Staff have not received any security awareness training.
- The EHR vendor contract has not been reviewed for Business Associate Agreement (BAA) compliance.
- Physical access to the server closet (which houses routers and a shared NAS) is not restricted — it doubles as a supply room.

---

*This scenario is a fictional practice exercise for cybersecurity audit and controls assessment training.*
