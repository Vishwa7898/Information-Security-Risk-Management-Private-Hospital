# Information Security Risk Management – MediCare Plus Private Hospital

## IT3070 – Information Assurance & Security

This repository contains the group assignment for identifying critical information assets and assessing information-security risks at **MediCare Plus Private Hospital (Pvt) Ltd**, a medium-sized private hospital in Sri Lanka.

The assignment uses the Allegro critical information asset profile and information asset risk worksheets to describe important information assets, identify threats, estimate risk, and propose risk-treatment controls.

## Project Overview

MediCare Plus Private Hospital uses a computer-based Hospital Management System (HMS) to support clinical care and administrative operations. The assignment focuses on three critical information assets:

1. Employee Information System (EIS)
2. Hospital Billing & Payment Information (BPI)
3. Patient Medical Records (PMR)

Confidentiality, integrity, and availability are important across all three assets. A security incident could affect employee privacy, financial operations, patient privacy, clinical decisions, and hospital services.

## Group Information

| Student ID | Student | Assigned information asset |
|---|---|---|
| IT23579736 | Wijethunga P.V.N.M. | Employee Information System (EIS) |
| IT23702172 | Soysa W.C.R. | Hospital Billing & Payment Information (BPI) |
| IT23824942 | M M W M Marasingha | Patient Medical Records (PMR) |

**Batch / Lab Group:** Y3.S2.WE.IT.0201

## Information Assets

### 1. Employee Information System (EIS)

The EIS stores and manages employee-related information used by Human Resources and authorized hospital administrators. Examples include employee personal details, employee IDs, job roles, departmental information, salary details, attendance, leave, and employment records.

**Owner:** Human Resources (HR) Department, MediCare Plus Private Hospital.

**Why it matters:** Unauthorized disclosure can violate employee privacy, unauthorized changes can affect salary or employment records, and downtime can delay HR operations.

**Key security considerations:**
- Restrict access to authorized HR staff and other users who need it for their duties.
- Maintain accurate records and traceable changes.
- Use role-based access control, least privilege, multi-factor authentication, access reviews, and monitoring.
- Protect systems and workstations from unauthorized physical access.

### 2. Hospital Billing & Payment Information (BPI)

Billing and payment information supports patient invoicing, treatment-charge records, payment processing, insurance payments, refunds, unpaid balances, and financial administration.

**Owner:** Finance and Billing Department.

**Why it matters:** Incorrect or unauthorized changes can lead to incorrect patient charges, payment disputes, financial loss, and reduced trust.

**Key security considerations:**
- Permit access only to appropriately authorized finance and billing personnel.
- Log changes to bills, refunds, payment status, and transaction records.
- Require additional approval for significant bill adjustments or refunds.
- Back up billing records and train employees on approved handling procedures.
- Protect finance-office computers and restrict physical access.

### 3. Patient Medical Records (PMR)

PMR contains highly confidential clinical information, including patient identifiers, medical history, diagnoses, allergies, laboratory and test results, prescriptions, treatments, doctors’ notes, and discharge summaries. The records are stored in the PMR database, attachments, and backups and are accessed through clinical workstations. Billing and employee records are outside this asset’s scope.

**Information owner:** Head of Medical Records, responsible for access approval, record quality, and risk decisions.  
**Technical custodian:** IT Manager, responsible for the application, database, backups, and implementation of access controls.

**Security requirements:**
- **Confidentiality:** Only authorized users should access the records needed for their duties.
- **Integrity:** Changes must be authorized and traceable, including the author, time, and previous value where applicable.
- **Availability:** Authorized clinical staff need timely access for emergency and routine care, with tested recovery and controlled downtime procedures.
- **Accountability and privacy:** Use individual user identities, traceable access, minimum-necessary use, and approved retention and disposal procedures.

The assignment identifies **integrity** as the most important security requirement for PMR, while also recognizing the importance of confidentiality and continuous availability.

## Risk Assessment Summary

The assignment identifies threats to each asset and considers the actor, means, motive, outcome, affected security requirements, probability, consequences, severity, and risk treatment.

### Example PMR risks

| Risk ID | Risk scenario | Main impact | Probability | Relative risk score | Treatment |
|---|---|---|---|---:|---|
| PMR-R1 | An employee with legitimate PMR access but excessive permissions exports records outside their care responsibilities and sells them to an external party. | Unauthorized disclosure; confidentiality and accountability are affected. | Medium (50%) | 17.0 | Mitigate |
| PMR-R2 | A phishing-led ransomware intrusion encrypts the PMR database, attachments, and reachable backups, disrupting clinical access. | Interruption and unauthorized encryption; availability and integrity are affected. | Medium (50%) | 25.0 | Mitigate first |

The probability figures are estimates used in the assignment’s risk worksheet, not measured incident statistics. The PMR-R2 scenario does not automatically assume that data was stolen or permanently destroyed; those possibilities require investigation.

## Proposed Risk Treatments and Controls

### Insider disclosure of patient records (PMR-R1)

- Apply role-based access control and least privilege, based on care assignment and job responsibilities.
- Require approval for exceptional access and review it promptly.
- Restrict unnecessary bulk exports and unapproved transfer channels.
- Centralize protected audit logs and alert on unusual searches and exports.
- Review alerts daily and periodically test whether monitoring detects misuse.
- Encrypt stored records and backups; use protected, approved transmission.
- Lock unattended screens, restrict removable media, train staff, and remove access promptly when roles change or employment ends.
- If an incident is detected, revoke access, preserve evidence, identify affected records and patients, and assess notification obligations.

**Residual risk:** A user may photograph a screen, monitoring may miss activity, and information already disclosed cannot reliably be recalled.

### Phishing-led ransomware affecting PMR (PMR-R2)

- Filter risky email attachments, patch endpoints, use endpoint detection, and train staff to report suspicious messages.
- Segment staff, server, and backup networks; separate administrative accounts from everyday accounts.
- Require strong multi-factor authentication for remote and administrative access.
- Maintain encrypted offline or immutable backups with separate credentials.
- Test restoration regularly and verify that recovery copies are clean.
- Prepare a clinical downtime plan, including controlled paper records with patient identifiers, timestamps, and staff sign-off.
- During an incident, isolate affected devices and network segments, preserve evidence, and block compromised credentials.
- Restore from a verified clean point, validate patient identities, allergies, and medications with clinical staff, then reopen services in phases and reconcile downtime records.

The assignment proposes recovery targets for PMR of **RTO: 4 hours** and **RPO: 1 hour**, subject to clinical approval. These are proposed targets, not a claim that the current system already meets them.

## Risk Prioritization

Based on the PMR risk scores recorded in the assignment, ransomware disruption (PMR-R2, 25.0) is prioritized for mitigation before the insider disclosure scenario (PMR-R1, 17.0). Both risks require treatment because of their potential effects on patient care, privacy, and hospital operations.

Risk treatment options considered in the worksheets include:

- **Accept:** Retain the risk when the decision is justified and approved.
- **Defer:** Postpone action where justified, with the risk documented and reviewed.
- **Mitigate:** Reduce likelihood and/or impact by applying controls.
- **Transfer:** Shift part of the financial or operational consequences to another party, where appropriate; this does not remove all responsibility.

## Risk Management Approach

The assignment follows these main steps:

1. Identify and describe the critical information asset.
2. Identify the information owner and applicable security requirements.
3. Describe realistic threat scenarios by considering the actor, means, motive, and outcome.
4. Estimate probability and assess consequences across relevant impact areas.
5. Calculate and compare relative risk scores using the assignment worksheets.
6. Select a risk-treatment decision.
7. Propose administrative, technical, and physical controls.
8. Record residual risks that remain after controls are applied.

## Key Security Concepts

- **Confidentiality:** Information is available only to authorized people.
- **Integrity:** Information remains accurate, complete, and protected from unauthorized changes.
- **Availability:** Information and systems are accessible to authorized users when needed.
- **Least privilege:** Users receive only the access required for their responsibilities.
- **Role-based access control (RBAC):** Permissions are assigned according to job roles.
- **Multi-factor authentication (MFA):** Access requires more than one authentication factor.
- **Audit logging:** Access and changes are recorded to support monitoring and investigation.
- **Residual risk:** The risk that remains after controls have been applied.
- **RTO:** Target time for restoring a service after disruption.
- **RPO:** Target maximum period of data loss measured in time.

## References

The assignment’s reference list includes the following security guidance and standards:

1. Cybersecurity and Infrastructure Security Agency (CISA), **Secure Our World**: https://www.cisa.gov/cybersecurity-awareness-month
2. National Institute of Standards and Technology (NIST), **Digital Identity Guidelines: Authentication and Authenticator Management, SP 800-63B**: https://pages.nist.gov/800-63-4/sp800-63b.html
3. National Institute of Standards and Technology (NIST), **Security and Privacy Controls for Information Systems and Organizations, SP 800-53 Rev. 5**: https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final
4. Cybersecurity and Infrastructure Security Agency (CISA), **Insider Threat Mitigation Guide**: https://www.cisa.gov/sites/default/files/2022-11/Insider%20Threat%20Mitigation%20Guide_Final_508.pdf
5. PCI Security Standards Council, **PCI Data Security Standard (PCI DSS)**: https://www.pcisecuritystandards.org/standards/pci-dss/


This repository presents an academic information-security risk assessment based on the assignment scenario. Risk estimates and proposed controls are for the coursework context and should not be interpreted as confirmation of the hospital’s actual security posture or regulatory compliance.
