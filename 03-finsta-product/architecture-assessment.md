# FiNSTA Product Architecture Assessment

## Executive Summary (Board-facing)

FiNSTA is Kapil IT Solutions' primary revenue asset and the product most exposed to both competitive risk and regulatory change. The assessment framework below identifies five critical dimensions requiring investment: architecture modernisation, QA transformation, third-party dependency health, AI/ML integration, and SaaS delivery model transition. These investments are necessary to defend existing NBFC clients against next-generation competitors and to unlock the product-led growth required to scale the client base.

**Recommended investment horizon:** 18 months | **Architecture risk level:** 🔴 High (pending internal discovery) | **Regulatory exposure:** 🔴 High (DPDP Act 2023, RBI Digital Lending 2022)

---

## Architecture Audit Framework

### Maturity Levels
Use this scale to assess FiNSTA's current state after codebase walk-through (Days 10–14):

| Level | Description | Typical indicators |
|-------|-------------|-------------------|
| L1 — Monolith | Single deployable unit, shared database, tightly coupled modules | Any change requires full regression; database is the integration point |
| L2 — Modular monolith | Logical modules with defined boundaries, still one deployment | Module-level test suites; some internal APIs; deployable as one unit |
| L3 — Service-oriented | Selected services extracted, shared infrastructure | Separate repos for 2–3 key domains; REST APIs between services |
| L4 — Microservices | Domain-driven service boundaries, independent deployability | Each service owns its data; CI/CD per service; event-driven async |

> **[REQUIRES INTERNAL DISCOVERY — method: codebase walk-through with lead architect, Day 10–14]**
> Current FiNSTA architecture level: ___
> Target architecture level (18 months): L3 (modular monolith → selective microservices)

### Recommended Target Architecture
Given CMMI L3 maturity and the team size (~232 total, engineering subset TBD):

- **Phase 1 (0–6 months):** Stabilise the modular monolith — enforce module boundaries, introduce internal API contracts, eliminate cross-module direct database access
- **Phase 2 (6–12 months):** Extract high-value microservices — Loan Origination, Compliance Reporting, Notifications
- **Phase 3 (12–18 months):** Full API-first product with OpenAPI 3.0 specs; multi-tenant SaaS on AWS ap-south-1

---

## Tech Debt Scoring Matrix

Score each dimension 1–5 after internal discovery. Current scores are placeholder estimates based on CMMI L3 baseline and product vintage.

| Dimension | Estimated current (1–5) | Target (18 months) | Gap | Priority |
|-----------|------------------------|-------------------|-----|----------|
| Code quality (test coverage, linting) | 2 | 4 | High | 🔴 P1 |
| Automated test coverage % | 1–2 | 4 | Critical | 🔴 P1 |
| Dependency health (CVEs, licence risk) | 2 | 4 | High | 🔴 P1 |
| API surface area (OpenAPI coverage) | 2 | 5 | High | 🟡 P2 |
| CI/CD pipeline maturity | 2 | 4 | High | 🟡 P2 |
| Mobile platform parity (iOS/Android) | 3 | 4 | Medium | 🟡 P2 |
| Documentation quality | 2 | 4 | High | 🔵 P3 |
| Observability (logging, tracing, metrics) | 2 | 4 | High | 🟡 P2 |

> **Score definitions:** 1 = absent/ad-hoc | 2 = basic/manual | 3 = defined but inconsistent | 4 = automated and consistent | 5 = optimised and measured

---

## QA Gap Analysis

### Context
Market intelligence (ZoomInfo, May 2026) confirms QA remediation is actively planned internally. As CTO, move ahead of this signal — define and own the QA transformation plan before it becomes a reactive exercise.

### Likely Current State
| Indicator | Estimated state | Evidence basis |
|-----------|----------------|----------------|
| Automated test coverage | <20% | CMMI L3 does not require automation; no public signals of test automation tooling |
| Test types in use | Primarily manual functional testing | Typical for products of this vintage and domain |
| Regression cycle time | 2–5 days | Manual regression on NBFC loan flows is inherently lengthy |
| Defect escape rate to production | Unknown | `[REQUIRES INTERNAL DISCOVERY]` |
| QA team structure | Separate QA team, late-stage testing | CMMI L3 typically implies defined but siloed QA |

### Target State (90 days)
```
Test Pyramid:
  ┌─────────────────────┐
  │   E2E Tests (10%)   │  Playwright / Cypress
  ├─────────────────────┤
  │ Integration (20%)   │  API contract tests
  ├─────────────────────┤
  │   Unit Tests (70%)  │  JUnit / Jest / pytest
  └─────────────────────┘
```

### QA Transformation Roadmap
| Action | Timeline | Owner | Tool |
|--------|----------|-------|------|
| Automate top 10 critical loan flow regression paths | Days 31–45 | QA Lead + SDET | Playwright/Cypress |
| Add API contract tests for CIBIL, CERSAI, e-KYC integrations | Days 31–60 | Backend + QA | Pact / REST Assured |
| Introduce SDET role (hire or retrain) | Days 45–60 | CTO + HR | N/A |
| Integrate automated tests into CI pipeline | Days 46–75 | DevOps + QA | GitHub Actions |
| Define defect escape rate SLA (<2% to production) | Days 61–75 | CTO + QA Lead | Jira metrics |
| Achieve 50% automation coverage on core flows | Month 3 | QA CoE | All above |
| Achieve 80% automation coverage | Month 6 | QA CoE | All above |

---

## Third-Party Library Assessment

### Context
An RFP for third-party library initiatives is expected within 3 months (ZoomInfo, May 2026). Define selection criteria first — own the process, don't react to it.

### Dependency Audit Scope
- [ ] Generate SBOM (Software Bill of Materials) — tools: CycloneDX or OWASP Dependency-Track
- [ ] Scan all dependencies for known CVEs — tool: Snyk or OWASP Dependency-Check
- [ ] Identify outdated packages (>2 major versions behind)
- [ ] Audit licence compliance: flag GPL/AGPL libraries in commercial product
- [ ] Identify vendor lock-in risk: proprietary SDKs with no open alternatives

### Library Selection Criteria (for RFP)
When evaluating third-party library replacements, score on:

| Criterion | Weight |
|-----------|--------|
| Active maintenance (commits in last 6 months) | 25% |
| CVE history and patch responsiveness | 25% |
| Open source licence (MIT/Apache preferred) | 15% |
| Community size and documentation quality | 15% |
| Performance benchmarks vs. current | 10% |
| Integration effort (migration complexity) | 10% |

---

## AI/ML Integration Opportunities

FiNSTA has no known AI/ML capabilities currently. This is the largest competitive gap against next-generation NBFC platforms.

### Prioritised opportunities

| Opportunity | Business value | Effort | Priority |
|-------------|---------------|--------|----------|
| ML-based credit scoring | Reduce default rate; faster approvals | L | 🟡 P2 |
| LLM-powered document parsing (loan applications, KYC docs) | 60% reduction in manual data entry | M | 🟡 P2 |
| Fraud detection (anomaly detection on transaction patterns) | Reduce fraudulent disbursements | M | 🟡 P2 |
| AI-assisted collections prioritisation | Improve delinquency recovery rates | M | 🔵 P3 |
| Chatbot for borrower self-service | Reduce support volume | S | 🔵 P3 |

### ML Credit Scoring Implementation Path
```
Phase 1: Data foundation (Month 4–6)
  → Instrument FiNSTA to log all credit decisions and outcomes
  → Build feature pipeline from: bureau data (CIBIL/Experian) + 
    internal repayment history + AA-consented financial data

Phase 2: Model development (Month 7–9)
  → Train baseline model: Gradient Boosting (XGBoost/LightGBM)
  → Evaluate vs. current rule-based scoring
  → RBI model explainability requirement: use SHAP values

Phase 3: Production deployment (Month 10–12)
  → Shadow mode: run model alongside human underwriting
  → Measure: approval rate delta, default rate delta
  → Full rollout with human override capability
```

---

## SaaS Transformation Plan

### Current delivery model
> **[REQUIRES INTERNAL DISCOVERY — method: sales team + infrastructure team interview]**
> Likely: client-hosted on-premise or dedicated hosted instances. Multi-tenancy unknown.

### Target delivery model
**Multi-tenant SaaS on AWS India region (ap-south-1)**

| Capability | Current | Target | Timeline |
|-----------|---------|--------|----------|
| Deployment model | Per-client instance | Multi-tenant SaaS | Month 10–12 |
| Infrastructure | On-premise / hosted | AWS ap-south-1 | Month 7–9 |
| Data isolation | Database per client | Row-level security + schema separation | Month 8–10 |
| Uptime SLA | Unknown | 99.9% (8.7 hr/yr downtime budget) | Month 10 |
| Pricing model | Perpetual licence | Subscription (monthly/annual) | Month 6 |
| Self-serve onboarding | No | Yes (target) | Month 12 |

### Data residency (RBI compliance)
All NBFC client data must reside in India. AWS ap-south-1 (Mumbai) is the required region. Confirm no data flows through us-east-1 or other non-India regions.

---

*Back to [README](../README.md) | Next: [Modernisation Roadmap →](./modernisation-roadmap.md)*
