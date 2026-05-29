# RBI & Regulatory Compliance Gap Matrix

## Executive Summary (Board-facing)

FiNSTA operates in one of India's most heavily regulated technology sectors. Three regulatory frameworks enacted between 2022 and 2023 — RBI Digital Lending Guidelines 2022, DPDP Act 2023, and CERT-In Directions 2022 — create mandatory engineering requirements that must be implemented before Q2. Non-compliance exposes both Kapil IT Solutions and its NBFC clients to regulatory action, reputational damage, and financial penalties. Full compliance is also a competitive differentiator: FiNSTA should market itself as "RBI Digital Lending 2022 compliant out-of-box" — a claim few competitors can make for the Nidhi/MACS segment.

---

## Applicable Regulatory Frameworks

| Framework | Issuing authority | Applicability to FiNSTA | Urgency |
|-----------|------------------|------------------------|---------|
| RBI Master Directions for NBFCs 2016 | RBI | Core operational framework for all NBFC clients | 🔴 Active |
| RBI Digital Lending Guidelines 2022 | RBI | Any digital lending flow in FiNSTA | 🔴 Immediate |
| Digital Personal Data Protection (DPDP) Act 2023 | MeitY / GoI | All borrower personal data processed by FiNSTA | 🔴 Immediate |
| CERT-In Directions 2022 | CERT-In / MeitY | All IT systems serving financial institutions | 🔴 Immediate |
| Account Aggregator (AA) Framework | RBI + ReBIT | Credit assessment using consented financial data | 🟡 High |
| CERSAI Integration | CERSAI / RBI | Secured lending workflows | 🟡 High |
| e-KYC (UIDAI / Aadhaar) | UIDAI | Customer onboarding in FiNSTA | 🟡 High |
| NACH / eNACH | NPCI | Loan repayment collection | 🟡 High |
| IT Act 2000 + Amendment 2008 | GoI | All electronic records and digital signatures | 🔵 Ongoing |
| Fair Practice Code for NBFCs | RBI | Borrower-facing features in FiNSTA | 🔵 Ongoing |
| CIBIL / Credit Bureau API | TransUnion CIBIL | Credit assessment | 🔵 Active |

---

## Detailed Gap Assessment

### 1. RBI Digital Lending Guidelines 2022 — 🔴 Critical

**What is required:**

| Requirement | Description | Current status |
|-------------|-------------|----------------|
| Key Fact Statement (KFS) | Borrower must receive a KFS before loan acceptance: APR, total cost, EMI, penalties | `[REQUIRES INTERNAL DISCOVERY]` |
| LSP disclosure | All Loan Service Provider names must be disclosed on app/portal | `[REQUIRES INTERNAL DISCOVERY]` |
| Cooling-off period | Borrower must be able to exit loan within cooling-off period (specified by NBFC) with only pro-rata interest | `[REQUIRES INTERNAL DISCOVERY]` |
| Disbursement to own account | Loan disbursement only to borrower's bank account — no third-party disbursement | `[REQUIRES INTERNAL DISCOVERY]` |
| Consent architecture | Explicit consent required before accessing borrower's phone data (no camera, microphone, contacts, location without specific consent) | `[REQUIRES INTERNAL DISCOVERY]` |
| Grievance redressal | In-app grievance mechanism with designated officer details | `[REQUIRES INTERNAL DISCOVERY]` |

**Risk if non-compliant:** RBI can direct NBFC clients to cease digital lending operations. Client contracts may include compliance warranties — non-compliance triggers liability.

**Remediation effort:** M — 6–8 weeks of engineering, primarily UI changes + backend KFS generation logic

---

### 2. Digital Personal Data Protection (DPDP) Act 2023 — 🔴 Critical

**What is required:**

| Requirement | Description | Engineering implication |
|-------------|-------------|------------------------|
| Consent management | Explicit, informed, granular consent before collecting personal data | Build consent management module — separate consent per data category |
| Data principal rights | Right to access, correct, erase, and port personal data | API endpoints for all four rights; workflow for erasure requests |
| Data fiduciary registration | Register as data fiduciary with Data Protection Board | Legal + compliance — not an engineering task, but triggers it |
| Data minimisation | Collect only data necessary for the stated purpose | Audit all data collection points in FiNSTA |
| Cross-border transfer controls | Personal data transfer outside India requires Board approval or adequate protection | Verify no data flows to non-India cloud regions |
| Breach notification | Notify Data Protection Board of breaches within a prescribed timeline | Build breach detection and notification pipeline |

**Penalties:** Up to ₹250 crore per violation.

**Key note:** ISO 27001 certification (which Kapil IT holds) addresses information security policies. DPDP Act requires additional engineering controls — they are complementary, not substitutes.

**Remediation effort:** XL — consent module is a significant new feature; rights management requires database schema changes and new APIs

---

### 3. CERT-In Directions 2022 — 🔴 Critical

**What is required:**

| Requirement | Specification | Current status |
|-------------|--------------|----------------|
| Breach notification | Report cybersecurity incidents to CERT-In within **6 hours** of detection | `[REQUIRES INTERNAL DISCOVERY]` |
| Log retention | Maintain logs of all ICT systems for **180 days** within India | `[REQUIRES INTERNAL DISCOVERY]` |
| VPN and cloud service provider reporting | Maintain subscriber records; report on request | Applicable if VPN services used |
| Synchronise system clocks | All ICT infrastructure must sync with NTP servers specified by CERT-In | Infrastructure task |
| Designated PoC | Designate a point of contact for CERT-In reporting | Assign immediately |

**Risk if non-compliant:** Criminal liability for non-reporting. FiNSTA serves live financial institutions — a breach would be high-profile and regulatorily significant.

**Remediation effort:** M — log aggregation (ELK/CloudWatch), automated incident detection (PagerDuty + SIEM), 6-hour notification workflow

---

### 4. Account Aggregator (AA) Framework — 🟡 High Priority

**What is the opportunity:**
The AA framework (live in India since 2021) allows NBFCs to pull consented financial data from banks and other financial institutions for credit assessment — with the borrower's explicit consent. FiNSTA acting as a **Financial Information User (FIU)** enables real-time, consent-based access to bank statements, insurance data, and tax records.

**Competitive impact:** AA-ready NBFC software is a strong differentiator. It reduces the cost and time of credit assessment dramatically for the underserved MSME and rural borrower segments that FiNSTA's clients serve.

**Technical requirements:**
- Integrate with AA ecosystem via ReBIT-specified API specifications
- Implement consent artefact management (creation, revocation, status tracking)
- Build data flow from AA to credit assessment module in FiNSTA
- Comply with AA data usage restrictions: use only for the consented purpose

**Remediation effort:** L — significant integration work; ReBIT API spec is well-documented

---

### 5. CERSAI Integration — 🟡 High Priority

**What is required:**
CERSAI (Central Registry of Securitisation Asset Reconstruction and Security Interest) requires registration of security interests within 30 days of charge creation. For FiNSTA NBFC clients doing secured lending, this must be automated.

**Current likely state:** Manual or semi-automated CERSAI filing. `[REQUIRES INTERNAL DISCOVERY]`

**Target state:** Automated CERSAI charge registration triggered by loan disbursement event in FiNSTA. Filing confirmation stored against loan record. Reminder workflow for any failed filings.

**Remediation effort:** S — API integration with CERSAI portal; workflow automation within existing loan lifecycle module

---

## Compliance Risk Matrix

| Framework | Likelihood of gap | Impact if non-compliant | Overall risk |
|-----------|------------------|------------------------|--------------|
| RBI Digital Lending 2022 | 🔴 High | 🔴 Critical | 🔴 Act immediately |
| DPDP Act 2023 | 🔴 High | 🔴 Critical | 🔴 Act immediately |
| CERT-In 2022 | 🟡 Medium | 🔴 Critical | 🔴 Act immediately |
| AA Framework | 🔴 High (not integrated) | 🟡 Competitive risk | 🟡 Q2 priority |
| CERSAI automation | 🟡 Medium | 🟡 Client risk | 🟡 Q2 priority |
| e-KYC / UIDAI | 🔵 Low (likely integrated) | 🟡 High | 🔵 Verify and maintain |
| NACH / eNACH | 🔵 Low (likely integrated) | 🟡 High | 🔵 Verify and maintain |

---

## Remediation Roadmap

| Action | Owner | Timeline | Effort | Compliance framework |
|--------|-------|----------|--------|---------------------|
| KFS generation module | Engineering | Month 2–3 | M | RBI DL 2022 |
| LSP disclosure in UI | Engineering | Month 1 | S | RBI DL 2022 |
| Cooling-off period enforcement | Engineering | Month 2 | S | RBI DL 2022 |
| Grievance redressal in-app | Engineering | Month 2 | S | RBI DL 2022 |
| Consent management module | Engineering | Month 3–5 | XL | DPDP 2023 |
| Data principal rights APIs | Engineering | Month 4–6 | L | DPDP 2023 |
| Data classification audit | Engineering + Legal | Month 1–2 | M | DPDP 2023 |
| CERT-In PoC designation | CTO + Legal | Day 7 | S | CERT-In 2022 |
| 180-day log retention setup | DevOps | Month 2 | M | CERT-In 2022 |
| 6-hour breach notification pipeline | Engineering + DevOps | Month 2–3 | M | CERT-In 2022 |
| CERSAI automation | Engineering | Month 4–5 | S | RBI / CERSAI |
| AA framework (FIU) integration | Engineering | Month 4–6 | L | AA Framework |

---

## Compliance RAG Dashboard (update quarterly)

| Framework | Status | Last reviewed | Owner |
|-----------|--------|--------------|-------|
| RBI Digital Lending 2022 | 🔴 Not assessed | — | CTO + Legal |
| DPDP Act 2023 | 🔴 Not assessed | — | CTO + Legal |
| CERT-In 2022 | 🔴 Not assessed | — | CTO + IT Security |
| AA Framework | 🔴 Not integrated | — | CTO + Engineering |
| CERSAI | 🟡 Unknown | — | Engineering Lead |
| e-KYC / UIDAI | 🟡 Unknown | — | Engineering Lead |
| NACH / eNACH | 🟡 Unknown | — | Engineering Lead |

> Update this table after Day 21 compliance review with legal team.

---

*Back to [README](../README.md)*
