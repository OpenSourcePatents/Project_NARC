# Data Flow Architecture

## Unified Data Lake and Tiered Access Model

---

## Tiered Access Partitions

### TIER 1: UNCLASSIFIED / LAW ENFORCEMENT SENSITIVE (LES)
**Accessible to:** All participating law enforcement (federal, state, local, tribal)

| Data Type | Source |
|---|---|
| NARC CRI alerts and geographic heatmaps | NARC engine |
| ODMAP overdose events | 5,300+ agencies |
| OD death reports with toxicology summaries (no PII) | Medical examiners, NFLIS |
| Dealer territory heat maps | OD clustering analysis |
| Public social media dealer indicators | SOCIAL SCAN |
| OFAC SDN list entities | Treasury/OFAC |
| DEA SSL chemical watch list | DEA |
| Precursor seller advertisements | PRECURSOR WATCH |
| Case status tracking | CASE BUILDER |
| NFLIS forensic drug analysis summaries | DEA NFLIS |
| Batch signature clusters | Toxicology analysis |

### TIER 2: SENSITIVE BUT UNCLASSIFIED (SBU) / FOR OFFICIAL USE ONLY (FOUO)
**Accessible to:** Federal law enforcement, state task force officers with clearance/NDA

| Data Type | Source |
|---|---|
| Resolved dealer profiles (PII) | IDENTITY FUSION |
| FinCEN BSA/SAR financial intelligence | FinCEN |
| Blockchain wallet clustering and transaction maps | CHAIN TRACE |
| Payment platform records (via legal process) | PAYMENT TRACE |
| Trade-based money laundering anomaly scoring | TRADE TRAP |
| Victim-to-dealer communication chains (via warrant) | OD MAP |
| Precursor shipment tracking data | CBP / PRECURSOR WATCH |
| Active investigation de-confliction flags | NFOC |
| CASE BUILDER prosecution packages | CASE BUILDER |

### TIER 3: CLASSIFIED
**Accessible to:** Cleared federal personnel with need-to-know

| Data Type | Source |
|---|---|
| HUMINT source reporting | DEA/FBI |
| Foreign intelligence on cartel operations | IC |
| JITC-CC operational intelligence | DOD |
| Diplomatic communications on precursor controls | State Dept |
| Covert surveillance data | Multiple |
| Ongoing undercover operation details | DEA/FBI |

## Input Sources

```
ODMAP (5,300 agencies)          -->  [UNIFIED DATA LAKE]
State Medical Examiners         -->  [UNIFIED DATA LAKE]
EMS/Naloxone Reports            -->  [UNIFIED DATA LAKE]
Local PD Incident Reports       -->  [UNIFIED DATA LAKE]
SOCIAL SCAN (social media)      -->  [UNIFIED DATA LAKE]
DARK WATCH (darknet)            -->  [UNIFIED DATA LAKE]
PAYMENT TRACE (financial)       -->  [UNIFIED DATA LAKE]
CHAIN TRACE (blockchain)        -->  [UNIFIED DATA LAKE]
PRECURSOR WATCH (sellers)       -->  [UNIFIED DATA LAKE]
TRADE TRAP (TBML)               -->  [UNIFIED DATA LAKE]
CBP Seizure Data                -->  [UNIFIED DATA LAKE]
NFLIS Lab Results               -->  [UNIFIED DATA LAKE]
FinCEN BSA/SAR                  -->  [UNIFIED DATA LAKE]
OFAC SDN Updates                -->  [UNIFIED DATA LAKE]
Court Records (PACER)           -->  [UNIFIED DATA LAKE]
JITC-CC Intel                   -->  [UNIFIED DATA LAKE]
```

## Output Consumers

```
[UNIFIED DATA LAKE]  -->  DEA Field Divisions (23)
[UNIFIED DATA LAKE]  -->  FBI JCODE
[UNIFIED DATA LAKE]  -->  HSI Field Offices
[UNIFIED DATA LAKE]  -->  CBP Port Directors
[UNIFIED DATA LAKE]  -->  HIDTA Task Forces (33)
[UNIFIED DATA LAKE]  -->  State Task Forces
[UNIFIED DATA LAKE]  -->  County Sheriffs
[UNIFIED DATA LAKE]  -->  U.S. Attorneys (94 districts)
[UNIFIED DATA LAKE]  -->  State AGs (50)
[UNIFIED DATA LAKE]  -->  FinCEN Analysts
[UNIFIED DATA LAKE]  -->  OFAC Targeting
[UNIFIED DATA LAKE]  -->  IRS-CI Agents
[UNIFIED DATA LAKE]  -->  EPIC Analysts
[UNIFIED DATA LAKE]  -->  ONDCP Policy
[UNIFIED DATA LAKE]  -->  Congressional Oversight
[UNIFIED DATA LAKE]  -->  DOD/NORTHCOM
```

## API Integration Model

ODMAP already supports API integration with 25 state systems. This model extends to all data sources.

**Requirements:**
- RESTful API endpoints for all data ingestion and consumption
- Standardized data schemas per module
- Real-time event streaming for fast-tier data (ODMAP, EMS, SOCIAL SCAN)
- Batch processing for slow-tier data (toxicology, court records, SUDORS)
- Webhook alerting for NARC CRI threshold crossings

## Security Architecture

- FedRAMP High authorized cloud environment
- Role-based access control (RBAC) enforcing tiered data access
- Audit logging on all queries and data access
- Encryption at rest and in transit
- Multi-factor authentication for all users
- Incident response protocols for data breach
- Annual security assessment by independent auditor
