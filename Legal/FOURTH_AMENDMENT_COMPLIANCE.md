# Fourth Amendment Compliance

## Constitutional Framework for All System Modules

---

## Core Principle

Every element of the Total Kill Chain architecture operates within existing legal authorities or requires only standard judicial process (warrants, subpoenas, court orders) that is already routinely obtained in federal drug investigations.

No module conducts warrantless surveillance of protected communications. No module targets protected speech. No module generates automated prosecutions without human review.

## Module-by-Module Legal Basis

| Module | Data Type | Legal Authority | Warrant Required? |
|---|---|---|---|
| NARC | Aggregate OD events, anonymized | Public health data | No |
| SOCIAL SCAN | Public social media posts | Public information doctrine | No |
| SOCIAL SCAN | Non-public content/DMs | 18 U.S.C. 2703 (SCA) | Yes (warrant or court order) |
| DARK WATCH | Darknet marketplace content | Established LE monitoring | No (undercover authority) |
| PAYMENT TRACE | Financial records | Grand jury subpoena / RFPA | Court order |
| PAYMENT TRACE | Blockchain transactions | Public ledger | No |
| OD MAP | Aggregate public health data | Public data | No |
| OD MAP | Individual victim phone | Search warrant | Yes |
| IDENTITY FUSION | LE database queries | Existing LE access | No |
| IDENTITY FUSION | IP/subscriber information | 18 U.S.C. 2703(d) | Court order |
| CASE BUILDER | Compiled evidence | Derived from lawful sources | N/A |
| SUPPLIER TRACE | Post-arrest device forensics | Search warrant incident to arrest | Yes |

## Privacy Safeguards

1. **Judicial oversight.** All non-public data collection conducted under judicial process.

2. **No speech targeting.** Public social media monitoring identifies commercial drug transaction patterns, not opinions, political expression, or protected speech.

3. **Human review required.** Automated identification generates leads for human review, not automated prosecution. Every case package is reviewed by a DEA agent and an AUSA before any action is taken.

4. **Data retention limits.** Non-actionable information subject to retention policies preventing indefinite storage.

5. **Audit trail.** All queries and data access logged and auditable to prevent misuse.

6. **NARC privacy by design.** NARC stores no PII at any point. All event data anonymized at ingestion. HIPAA compliance is architectural, not policy-based -- the system makes it technically impossible to reconstruct individual identities.

7. **Tiered access enforcement.** Role-based access control (RBAC) ensures users only access data their legal authority permits.

## Key Distinctions

**Public vs. private data.** The system draws a bright line between public information (social media posts, blockchain transactions, published sanctions lists, aggregate health data) and private information (DMs, financial records, phone contents, IP addresses). Public data requires no legal process. Private data requires appropriate judicial authorization in every case.

**Detection vs. prosecution.** NARC and the public-facing modules detect patterns and generate leads. They do not prosecute. The legal process chain (subpoena, warrant, court order) is required before any private data enters the system and before any enforcement action is taken.
