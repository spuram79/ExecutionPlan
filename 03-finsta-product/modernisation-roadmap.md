# FiNSTA Modernisation Roadmap

## Roadmap Overview

| Quarter | Theme | Key deliverables |
|---------|-------|-----------------|
| Q1 (Month 1–3) | Stabilise & assess | Architecture baseline, QA automation started, CI/CD pilot, dependency audit |
| Q2 (Month 4–6) | Compliance & API-first | AA framework integration, DPDP consent module, OpenAPI specs, SaaS pricing introduced |
| Q3 (Month 7–9) | New capabilities | Collections module, ML credit scoring pilot, AWS migration POC |
| Q4 (Month 10–12) | SaaS launch | Multi-tenant SaaS on AWS ap-south-1, mobile UX refresh, CERT-In automation |
| Months 13–18 | Scale & optimise | AI underwriting in production, geographic expansion support, CMMI Level 4 readiness |

---

## Detailed Quarterly Breakdown

### Q1 — Stabilise & Assess (Months 1–3)

**Architecture:**
- Complete codebase walk-through and architecture documentation
- Define module boundaries for modular monolith refactoring
- Eliminate top 10 most critical cross-module database coupling points

**QA:**
- Automate critical loan flow regression paths (loan origination, disbursement, repayment)
- Introduce Playwright/Cypress for UI automation
- Add API contract tests for CIBIL and CERSAI integrations

**DevOps:**
- Stand up GitHub Actions CI pipeline on one module (pilot)
- Define branching strategy (trunk-based development)
- Instrument DORA metrics baseline

**Dependencies:**
- Generate SBOM
- Complete CVE scan — remediate all Critical and High severity findings
- Publish library selection criteria for RFP

**Effort estimate:** L (large) — cross-team, requires dedicated QA and DevOps capacity

---

### Q2 — Compliance & API-First (Months 4–6)

**Compliance (highest priority):**
- Ship DPDP Act 2023 consent management module
- Implement Key Fact Statement (KFS) generation per RBI Digital Lending 2022
- Add LSP (Loan Service Provider) disclosure to all borrower-facing screens
- Begin Account Aggregator (AA) framework integration (Financial Information User role)
- Automate CERSAI charge registration within FiNSTA loan closure workflow

**API & architecture:**
- Publish OpenAPI 3.0 specs for all core FiNSTA modules
- Implement API versioning strategy (URI versioning: /v1/, /v2/)
- Deploy API gateway (AWS API Gateway or Kong)
- Introduce feature flags (LaunchDarkly or Unleash) for controlled rollouts

**Commercial:**
- Design SaaS subscription pricing tiers (SME / Growth / Enterprise)
- Introduce subscription billing for all new client contracts
- Build client onboarding portal (Phase 1: guided setup wizard)

**Effort estimate:** XL (extra large) — compliance work is non-negotiable and deadline-driven

---

### Q3 — New Capabilities (Months 7–9)

**Product:**
- Launch Collections module (delinquency management, automated follow-up sequences, legal escalation workflow)
- Pilot ML credit scoring with 1–2 willing NBFC clients (shadow mode alongside existing underwriting)
- Mobile UX audit and redesign kickoff (offline-first for rural NBFC agents)

**Infrastructure:**
- AWS migration POC: deploy FiNSTA on ap-south-1 in parallel with existing infrastructure
- Define multi-tenant data isolation architecture
- Implement secrets management (HashiCorp Vault or AWS Secrets Manager)
- Conduct semi-annual penetration test

**Data & AI:**
- Instrument FiNSTA to log all credit decisions for ML training data pipeline
- Build feature pipeline from CIBIL + internal repayment history + AA-consented data
- Train baseline credit scoring model (XGBoost/LightGBM)

**Effort estimate:** XL — three parallel workstreams; requires ML Engineer hire/contract

---

### Q4 — SaaS Launch (Months 10–12)

**SaaS platform:**
- Go-live: multi-tenant FiNSTA SaaS on AWS ap-south-1
- Row-level security and schema-based tenant isolation
- 99.9% uptime SLA enforced by architecture (redundancy, auto-scaling, health checks)
- Self-serve client onboarding flow (Phase 1 launch)

**Compliance:**
- CERT-In 6-hour breach notification pipeline automated
- 180-day log retention policy enforced in all environments
- DPDP data principal rights portal (erasure, portability) live

**Mobile:**
- React Native / Flutter mobile app refresh launched
- Offline-first loan origination for low-connectivity environments
- WCAG 2.1 accessibility compliance

**Quality:**
- 80% automated test coverage on core loan flows achieved
- Full CI/CD pipeline across all FiNSTA modules
- SonarQube quality gates blocking broken builds

**Effort estimate:** XL — this is the most complex quarter; requires full team alignment

---

### Months 13–18 — Scale & Optimise

- ML-based credit scoring in full production (not shadow mode)
- LLM document parsing for loan application automation
- Developer portal for NBFC clients (self-serve API integration)
- Geographic expansion: product localisation for Tamil Nadu (Tamil language), Maharashtra
- CMMI Level 4 assessment initiated
- Embedded finance API for Kapil Group internal entities
- Collections module v2: predictive collections prioritisation using ML

---

## Modernisation Risk Register

| Risk | Likelihood | Impact | Mitigation |
|------|-----------|--------|------------|
| Client disruption during migration to SaaS | Medium | High | Parallel run; opt-in migration; dedicated migration support team |
| Regulatory non-compliance during development | Low | Critical | Compliance gate at end of every sprint; legal review of every RBI-impacted feature |
| ML model bias in credit scoring | Medium | High | SHAP value explainability; regular model audits; human override always available |
| Team capacity insufficient for roadmap scope | High | High | Hire 4–6 engineers in Q1–Q2; use contractors for ML workstream |
| Technical debt resurfacing during refactoring | Medium | Medium | Strangler Fig pattern for migrations; never big-bang rewrites |

---

*Back to [Architecture Assessment](./architecture-assessment.md) | Back to [README](../README.md)*
