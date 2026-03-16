# System Overview

## PROJECT NARC: TOTAL KILL CHAIN -- Architecture

---

## High-Level System Diagram

```
                          NARC (EARLY WARNING)
                     Real-time CRI Alerting Layer
                                |
        +-----------------------+-----------------------+
        |                       |                       |
  PRECURSOR WATCH         CHAIN TRACE            SOCIAL SCAN
  (Seller Index)      (Blockchain Intel)     (Social Media Intel)
        |                       |                       |
        +----------+------------+------------+----------+
                   |                         |
             TRADE TRAP                 DARK WATCH
          (TBML Detection)           (Darknet Intel)
                   |                         |
                   +------------+------------+
                                |
                          UNIFIED DATA LAKE
                     Tier 1 | Tier 2 | Tier 3
                                |
                   +------------+------------+
                   |                         |
            IDENTITY FUSION           PAYMENT TRACE
         (De-anonymization)        (Financial Intel)
                   |                         |
                   +------------+------------+
                                |
                          CASE BUILDER
                   (Prosecution Packages)
                                |
                          TARGET BOARD
                    (National Dashboard)
                                |
                           SURGE OPS
                   (Coordinated Arrests)
                                |
                        SUPPLIER TRACE
                    (Upstream Escalation)
                                |
                    INTELLIGENCE FEEDBACK
                     (Loop to all stages)
                                |
                          NARC (CRI)
                   (Measure effectiveness)
```

## Module Summary

| Module | Type | Function |
|---|---|---|
| NARC | Detection | Real-time overdose mapping with population-normalized Crisis Rate Index (CRI) and automated YELLOW/ORANGE/RED alerting |
| PRECURSOR WATCH | Intelligence | Monitors Chinese e-commerce for precursor sellers, cross-references OFAC/DEA sanctions and indictments |
| CHAIN TRACE | Financial | Blockchain analysis of crypto flows between cartel wallets, CMLOs, and precursor suppliers |
| TRADE TRAP | Financial | Detects trade-based money laundering via anomalous goods flows (Guangdong to Mexico) |
| BANK WATCH | Financial | Scores financial institutions by fentanyl corridor exposure using BSA/SAR data |
| SOCIAL SCAN | Enforcement | AI/NLP scanning of public social media for dealer advertising patterns |
| DARK WATCH | Enforcement | Darknet marketplace monitoring for fentanyl vendor identification |
| PAYMENT TRACE | Enforcement | P2P payment platform analysis (Cash App, Venmo, Zelle) and crypto tracing |
| OD MAP | Enforcement | Overdose death clustering, batch signature analysis, victim-to-dealer attribution |
| IDENTITY FUSION | Targeting | Cross-platform de-anonymization resolving digital identities to real individuals |
| CASE BUILDER | Prosecution | Automated evidence package assembly with priority scoring and jurisdiction routing |
| TARGET BOARD | Operations | Unified national targeting dashboard for all participating agencies |
| SUPPLIER TRACE | Intelligence | Post-arrest upstream escalation feeding intelligence back into all modules |

## Seven-Stage Workflow

| Stage | Function | Lead Agency |
|---|---|---|
| 1. Early Warning | NARC CRI detection and alerting | ONDCP/HIDTA, CDC |
| 2. Precursor Detection | Identify and index precursor sellers | DEA Diversion / OFAC |
| 3. Shipment Interdiction | Intercept precursor shipments | CBP / USPIS |
| 4. Financial Disruption | Trace and freeze financial flows | FinCEN / OFAC / IRS-CI |
| 5. Distribution Mapping | Map wholesale-to-retail networks | DEA SOD / EPIC |
| 6. Dealer ID and Prosecution | Find dealers, build cases, prosecute | DEA OD Justice / HIDTA / JCODE |
| 7. Intelligence Feedback | Every arrest feeds back to all stages | All agencies |

## Design Principles

1. **Single source of truth.** One platform. Every agency reads and writes to the same system.
2. **Write once, read many.** Data entered once is visible (at appropriate access levels) to all consumers.
3. **Tiered access.** County sheriff sees Tier 1. DEA SOD sees Tier 1+2. Cleared federal personnel see Tier 3.
4. **Credit sharing.** Every contribution is attributed. Local PD overdose report that leads to federal indictment = local PD gets credit.
5. **Bidirectional flow.** Intelligence flows up (local to federal) and down (federal to local).
6. **API-first.** Every data source connects via API. No manual entry of data that exists elsewhere.
