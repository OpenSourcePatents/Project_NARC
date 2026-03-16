# Module Definitions

## Detailed Specifications for All System Modules

---

## Detection Layer

### NARC (National Addiction Response Cartography)
**Type:** Real-time geospatial detection and alerting
**Function:** Tracks overdoses nationally, normalizes against population, flags crisis zones automatically
**Data sources:** ODMAP, EMS/NEMSIS, 911 dispatch, medical examiners, CDC SUDORS, hospital ED feeds
**Key output:** Crisis Rate Index (CRI) per jurisdiction with YELLOW/ORANGE/RED alerting
**Technical stack:** Ingestion layer (API connectors), processing layer (deduplication, geocoding, CRI computation), alert layer (threshold evaluation, notification), visualization layer (national heatmap with drill-down)
**Privacy:** No PII stored. All events anonymized at ingestion. HIPAA compliant by architecture.

---

## Financial Intelligence Layer

### PRECURSOR WATCH
**Type:** Open-source intelligence / supply chain monitoring
**Function:** Indexes Chinese e-commerce platforms and chemical supplier websites for entities advertising fentanyl precursor chemicals
**Data sources:** Chinese B2B platforms, OFAC SDN list, PACER indictments, DEA SSL, UN INCB ISSL
**Key output:** Living supplier index with sanctions/indictment cross-reference and "still active" flags
**Update cadence:** Continuous scraping with daily index refresh

### CHAIN TRACE
**Type:** Blockchain financial intelligence
**Function:** Analyzes cryptocurrency flows between cartel wallets, CMLOs, and precursor suppliers
**Data sources:** OFAC-designated addresses, court-filed wallets, blockchain explorers (BTC, Tron, ETH), Chainalysis/TRM Labs, FinCEN crypto SARs
**Key output:** Transaction graph mapping flows from U.S. drug cash conversion to Chinese suppliers. Wallet clustering for new address identification.
**Key insight:** 97% of Chinese precursor manufacturers accept crypto. Payment trail is entirely on-chain.

### TRADE TRAP
**Type:** Trade-based money laundering detection
**Function:** Identifies anomalous goods flows consistent with CMLO TBML patterns
**Data sources:** U.S. Census trade data, CBP import/export records, Mexican customs (bilateral), FinCEN TBML advisories
**Detection patterns:** Below-market electronics from Guangdong to Mexico, repeated small-value CMLO-associated shipments, sudden commodity spikes to Sinaloa/Jalisco importers
**Key output:** Anomaly-scored trade relationships ranked by TBML probability

### BANK WATCH
**Type:** Financial institution exposure scoring
**Function:** Scores banks, MSBs, and crypto exchanges by fentanyl corridor exposure
**Data sources:** FinCEN BSA filings/advisories, OFAC enforcement actions, court records, public compliance failures
**Key output:** Institutional risk scores for China-Mexico-U.S. fentanyl financial corridors

---

## Enforcement Layer

### SOCIAL SCAN
**Type:** Social media intelligence
**Function:** AI/NLP monitoring of public social media for fentanyl dealing indicators
**Data sources:** Public posts on Instagram, TikTok, Twitter/X, Facebook, YouTube, public Telegram channels
**Methods:** Behavioral pattern analysis (not just keyword matching): emoji combinations, post-delete cycles, DM redirect behavior, payment app linking, account migration after bans, cross-platform account linking
**Legal basis:** Public information, no warrant required. Non-public content via 18 U.S.C. 2703 with legal process.
**Key output:** Suspected dealer account list with platform, username, patterns, geographic indicators, linked accounts

### DARK WATCH
**Type:** Darknet marketplace intelligence
**Function:** Continuous monitoring of DNMs for fentanyl vendor identification
**Methods:** Automated scraping, vendor profiling (posting frequency, shipping indicators, pricing, reviews), crypto address extraction, cross-reference with surface web for de-anonymization
**Legal basis:** Established LE monitoring techniques. Undercover purchases under existing DEA authority.
**Key output:** Vendor profiles with crypto addresses, shipping patterns, de-anonymization leads

### PAYMENT TRACE
**Type:** Digital payment intelligence
**Function:** Financial flow analysis on P2P platforms and crypto linked to suspected dealers
**Data sources:** Cash App, Venmo, Zelle, PayPal records (via legal process), blockchain analysis
**Detection patterns:** High-frequency small-dollar inflows, rapid cash-out, geographic concentration matching distribution territory
**Legal basis:** Grand jury subpoena (18 U.S.C. 3486), RFPA court order. Blockchain analysis of public ledger needs no warrant.
**Key output:** Financial profiles, transaction volumes, buyer identification leads, money flow maps

### OD MAP
**Type:** Overdose death intelligence
**Function:** Aggregates OD death data nationally, extracts dealer-linked intelligence
**Data sources:** NARC/ODMAP events, medical examiner reports, police reports, EMS records, toxicology
**Methods:** Geographic/temporal clustering for dealer territory ID, toxicology batch signature analysis linking deaths to common supply, victim phone analysis protocol (with legal authority)
**Key output:** National OD heat map with dealer overlay, batch signature clusters, victim-to-dealer chains

---

## Targeting Layer

### IDENTITY FUSION
**Type:** Cross-platform de-anonymization
**Function:** Resolves digital dealer identities to real-world individuals
**Methods:** Cross-reference identifiers from all modules (usernames, wallets, phone numbers, shipping addresses) against NCIC, NLETS, NADDIS, state records, DMV. Link analysis via shared phone numbers, emails, device fingerprints, IP addresses (via 18 U.S.C. 2703(d)), payment overlaps.
**Key output:** Resolved identity packages: name, DOB, address, criminal history, digital accounts, financial profile, distribution volume estimate, linked OD deaths

### CASE BUILDER
**Type:** Automated prosecution assembly
**Function:** Compiles court-ready evidence packages for each resolved dealer
**Components:** Social media archives, financial records, victim communications, toxicology/autopsy, batch signatures, crypto chains, criminal history, witness statements, recommended charges, mandatory minimums
**Priority scoring:** (1) Linked fatalities, (2) Distribution volume, (3) Sales to minors, (4) Upstream connections, (5) Evidence strength
**Key output:** Ranked prosecution packages routed to appropriate U.S. Attorney's Office or state AG

---

## Operations Layer

### TARGET BOARD
**Type:** Unified national targeting dashboard
**Function:** Presents all case-ready targets to authorized users across all agencies
**Elements:** National map with dealer locations/priority, individual target cards, linked OD death counts, upstream/downstream network visualization, case status tracking

### SURGE OPS
**Type:** Coordinated national arrest operations
**Function:** Quarterly takedown operations targeting highest-priority dealers
**Model:** Simultaneous execution across districts, pre-coordinated with U.S. Attorneys via CASE BUILDER packages

### SUPPLIER TRACE
**Type:** Post-arrest upstream escalation
**Function:** Every arrested dealer generates intelligence on supply chain
**Methods:** Standardized interview protocol, device forensics (contact lists, encrypted messaging, financial apps, tracking numbers), cross-reference with FENTANYL KILL CHAIN financial intelligence
**Key output:** Continuous feedback loop connecting street arrests to wholesale and cartel networks
