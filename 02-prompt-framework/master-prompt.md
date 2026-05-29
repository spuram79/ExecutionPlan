# Master Prompt Framework — CTO Assessment Report

## Purpose
This document provides the master prompt system for generating each section of the CTO assessment report using AI tools. Each domain section uses a consistent base context with domain-specific variables.

---

## Base System Context (use for every section)

```
You are generating a CTO assessment report for Kapil IT Solutions (CMMI Level 3, ISO 9001, 
ISO 27001, NASSCOM certified), headquartered in Hyderabad, Telangana. Part of Kapil Group 
(35+ companies). ~232 employees, ~$14M revenue.

Flagship product: FiNSTA — a mobile and web-based NBFC lending management platform serving 
NBFCs, Nidhi companies, MACS, RRBs, PACS, and small cooperative banks. Additional products: 
EasyCHIT (chit fund management) and Hexabuild (construction ERP).

The CTO has full access to internal systems, teams, codebase, and clients.

Report audiences:
- PRIMARY: Board / Founders — strategic transformation roadmap, investment decisions, risk exposure
- SECONDARY: Engineering & Product teams — execution plan, architecture decisions, skill development

Output requirements:
- Use STAR format (Situation → Task → Action → Result) for all findings
- Quantify all gaps, issues, and recommendations wherever possible
- Structure every domain in three time horizons:
  (1) 30-day quick wins — no structural change, immediate impact
  (2) 90-day structural changes — team, process, and tooling changes
  (3) 12–18 month transformation — architecture, product, and market changes
- Always reference applicable regulations where relevant:
  RBI Master Directions for NBFCs 2016, RBI Digital Lending Guidelines 2022, 
  Account Aggregator (AA) framework, CERSAI, CIBIL, DPDP Act 2023, 
  IT Act 2000 (amended 2008), CERT-In directions 2022
- Flag any data point not yet confirmed with: [REQUIRES INTERNAL DISCOVERY — method: <how to get it>]
- Never hallucinate metrics, client names, or technology specifics
```

---

## Domain-Specific Prompts

### Domain 1: FiNSTA Product Architecture & Tech Debt

```
Using the base context above, generate the FiNSTA Product Architecture Assessment section.

Cover:
1. Architecture audit framework (monolith → modular → microservices maturity assessment)
2. Tech debt scoring matrix across: code quality, test coverage, dependency health, 
   API surface area, deployment pipeline maturity, mobile platform parity
3. QA gap analysis (context: QA remediation is actively planned per market intelligence)
4. Third-party library assessment (context: RFP expected within 3 months — define criteria)
5. AI/ML integration opportunities: credit scoring, document parsing, fraud detection, 
   collections prioritisation
6. SaaS transformation plan: on-premise → multi-tenant SaaS on AWS ap-south-1
7. Modernisation roadmap with effort estimates (T-shirt sizing: S/M/L/XL)

Audience: Board (investment case) + Engineering (technical plan)
Format: Executive summary (½ page) + detailed assessment with gap matrix + roadmap table
```

---

### Domain 2: RBI & Regulatory Compliance

```
Using the base context above, generate the Regulatory Compliance Gap Analysis section.

Cover:
1. Compliance scorecard across all applicable frameworks:
   - RBI Master Directions for NBFCs 2016
   - RBI Digital Lending Guidelines 2022 (Key Fact Statement, LSP disclosure, cooling-off, 
     disbursement-to-own-account rule)
   - Digital Personal Data Protection (DPDP) Act 2023
   - CERT-In Directions 2022 (6-hour breach reporting, 180-day log retention)
   - CERSAI integration for secured lending
   - Account Aggregator (AA) framework / ReBIT API spec
   - e-KYC (UIDAI / Aadhaar) compliance
   - NACH / eNACH (NPCI) integration
   - IT Act 2000 and Amendment 2008
   - Fair Practice Code for NBFCs

2. Risk matrix: likelihood × impact for each gap
3. Remediation roadmap with owners, timelines, and estimated engineering effort
4. Competitive insight: AA-readiness as a market differentiator

Audience: Board (risk exposure) + Legal/Engineering (remediation plan)
Format: Compliance scorecard table + risk matrix + remediation roadmap with RAG status
```

---

### Domain 3: Engineering Org & Developer Productivity

```
Using the base context above, generate the Engineering Organisation Assessment section.

Cover:
1. DORA metrics baseline plan (how to instrument and measure all four metrics)
2. Team Topology redesign proposal:
   - Stream-aligned teams: FiNSTA Lending, Compliance & Reporting, Mobile/UX
   - Platform team: DevOps & Infrastructure
   - Enabling teams: QA/Testing CoE, AI/ML Engineering
3. Current state gaps:
   - CI/CD pipeline maturity (CMMI L3 ≠ automated deployment)
   - Code review culture and PR cycle time
   - On-call and incident response process
   - Developer experience (local setup, documentation, cognitive load)
4. QA transformation plan (automated testing pyramid, SDET role, shift-left QA)
5. DevOps implementation roadmap (GitHub Actions, Terraform IaC, Docker/K8s)
6. Engineering KPI dashboard design (visible to Board monthly)

Audience: Board (org design and hiring plan) + Engineering (execution roadmap)
Format: Org chart proposal + DORA baseline plan + transformation roadmap
```

---

### Domain 4: Client Acquisition & GTM Strategy

```
Using the base context above, generate the GTM Strategy and Client Acquisition section.

Cover:
1. NBFC market opportunity sizing (India: 10,000+ RBI-registered NBFCs)
2. Competitive analysis: FiNSTA vs. Nucleus LoanVantage, Finflux, TechFini, Mphasis lending
3. Current GTM gaps: pricing model, sales motion, geographic concentration
4. SaaS pricing transition plan: perpetual licence → subscription tiers
   (Suggest: SME tier for Nidhi/MACS, Growth tier for mid-NBFCs, Enterprise tier for large NBFCs)
5. Product-led growth levers: AA-readiness, RBI Digital Lending 2022 compliance out-of-box, 
   self-serve onboarding
6. Kapil Group captive leverage strategy
7. Geographic expansion plan: AP/Telangana base → Tamil Nadu, Maharashtra, North India MSME belt
8. Adjacent product opportunities: Collections platform, Insurance distribution, Embedded finance API
9. 18-month revenue growth model (assumptions-based, placeholders for actuals)

Audience: Board (revenue growth roadmap) + Sales/Product (execution plan)
Format: Market sizing + competitive matrix + SaaS pricing table + expansion roadmap
```

---

### Domain 5: Skill Gaps & Upskilling Plan

```
Using the base context above, generate the Skill Gap Assessment and Upskilling Plan section.

Cover:
1. Skill gap matrix: current estimated level vs. 18-month target across:
   - Cloud-native (AWS/Azure) — architecture and operations
   - DevOps & CI/CD — pipeline, IaC, containers
   - API-first design — OpenAPI, API gateway, versioning
   - AI/ML engineering — model development, MLOps, LLM integration
   - Security engineering — SAST/DAST, secrets management, DPDP controls
   - Test automation — SDET, automation frameworks, shift-left
   - NBFC domain depth — regulatory knowledge, business logic preservation
2. Role-based learning paths (Backend Engineer, Frontend Engineer, QA Engineer, 
   DevOps Engineer, Tech Lead, Engineering Manager)
3. Certification tracks for team leads
4. In-house training programme design (internal workshops + external platforms)
5. Skills matrix survey template (to distribute in Week 1)
6. L&D budget estimate and timeline
7. Knowledge preservation plan: pair domain experts with new engineers

Audience: Engineering + HR (execution) | Board (L&D investment ask)
Format: Gap matrix table + role-based learning path cards + L&D budget estimate
```

---

## Report Assembly Order

Generate sections in this sequence for logical narrative flow:

1. Executive summary (board-facing, 2 pages max)
2. Company and product context (Domain overview)
3. FiNSTA architecture assessment (Domain 1)
4. Regulatory compliance gap analysis (Domain 2)
5. Engineering org assessment (Domain 3)
6. GTM strategy (Domain 4)
7. Skill gaps and upskilling plan (Domain 5)
8. 90-day execution plan
9. 18-month transformation roadmap
10. Appendices: discovery checklist, skills survey template, KPI dashboard design

---

*Back to [README](../README.md)*
