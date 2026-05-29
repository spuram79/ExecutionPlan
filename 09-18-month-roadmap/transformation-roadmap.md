# 18-Month Technology Transformation Roadmap

## Transformation Vision

> In 18 months, Kapil IT Solutions will have transformed FiNSTA from a compliance-risk, on-premise lending ERP into a **cloud-native, AA-ready, AI-enhanced SaaS platform** that is the most compliant, easiest-to-adopt NBFC lending software in India — with the engineering culture, team structure, and developer productivity to sustain that lead.

---

## Quarterly Milestone Summary

### Q1 (Months 1–3) — Stabilise, Baseline & Quick Wins

**Theme:** No client disruption. Measure everything. Fix the most urgent risks.

| Milestone | Owner | Success metric |
|-----------|-------|----------------|
| Current state assessment complete | CTO | All `[REQUIRES DISCOVERY]` items closed |
| DORA metrics baseline established | Platform Team | All 4 metrics tracked monthly |
| CERT-In PoC designated | CTO + Legal | Filing confirmed |
| RBI DL 2022 quick fixes live (LSP, grievance, cooling-off) | Engineering | Features shipped to production |
| SBOM generated; Critical CVEs resolved | Engineering | Zero Critical CVEs |
| CI/CD pipeline live on all modules | Platform Team | Every PR triggers build + tests |
| QA automation: 20% coverage on critical paths | QA CoE | 20 automated tests in CI |
| Team topology implemented | CTO + HR | 5 teams formed and operational |
| 4 critical hires onboarded | CTO + HR | DevOps Lead, SDET ×2, Compliance Eng Lead |
| Skills survey completed | CTO + HR | 100% engineer completion |

**Board KPI targets (end of Q1):**
- Deployment frequency: measured (baseline established)
- Open Critical CVEs: 0
- Compliance gap: CERT-In and RBI quick fixes addressed

---

### Q2 (Months 4–6) — Compliance & API-First

**Theme:** Ship the compliance module. Introduce SaaS pricing. Open the API.

| Milestone | Owner | Success metric |
|-----------|-------|----------------|
| DPDP consent management module live | Engineering | Consent captured for all new borrowers |
| KFS (Key Fact Statement) generation live | Engineering | 100% of new loans have KFS |
| AA framework (FIU) integration live | Engineering | Consent-based financial data available in credit assessment |
| CERSAI charge registration automated | Engineering | CERSAI filings triggered on loan closure |
| 180-day log retention live | Platform Team | Audit log confirms compliance |
| 6-hour breach notification pipeline built | Engineering + DevOps | Drill test passed |
| OpenAPI 3.0 specs published for all FiNSTA modules | Engineering | Developer documentation available |
| SaaS subscription pricing: all new contracts on subscription | Sales + CTO | 0 new perpetual licences signed |
| Test automation: 50% coverage on critical paths | QA CoE | 50 automated tests in CI |
| Deployment frequency: weekly releases | Platform Team | DORA metric confirmed |

**Board KPI targets (end of Q2):**
- DPDP compliance: 70%+ (consent module live; data rights module in progress)
- RBI Digital Lending 2022: 90% compliant
- New client acquisitions citing compliance differentiator: 2+
- DORA: Deployment frequency = weekly; Lead time < 2 weeks

---

### Q3 (Months 7–9) — New Capabilities & Cloud Migration

**Theme:** New product modules. AI pilot. Move to AWS.

| Milestone | Owner | Success metric |
|-----------|-------|----------------|
| Collections module launched | FiNSTA Lending Team | First 3 NBFC clients using it |
| ML credit scoring pilot (shadow mode) | AI/ML Enabling Team | Model running alongside human underwriting on 1 NBFC client |
| AWS ap-south-1 production environment live | Platform Team | FiNSTA running on AWS (parallel to existing) |
| Multi-tenant architecture POC complete | Engineering | 2 test tenants running on shared infrastructure |
| Data residency audit: all data confirmed in India | Platform + Legal | No data outside ap-south-1 |
| Mobile UX refresh: React Native/Flutter app launched | Mobile Team | App store release |
| Offline-first loan origination live | Mobile Team | Tested at zero-connectivity |
| DPDP data principal rights APIs live | Engineering | Erasure + portability endpoints functional |
| ML credit scoring: model accuracy benchmark published | AI/ML Team | F1 score baseline documented |
| Test automation: 70% coverage | QA CoE | Measured in CI dashboard |

**Board KPI targets (end of Q3):**
- Collections module: 3 active NBFC clients
- DORA: Deployment frequency = on-demand; Lead time < 1 week
- AWS migration: 50% of workloads on AWS
- NPS: +15 points from Day 1 baseline

---

### Q4 (Months 10–12) — SaaS Launch & Full Compliance

**Theme:** FiNSTA SaaS is live. Full compliance. Elite engineering performance.

| Milestone | Owner | Success metric |
|-----------|-------|----------------|
| FiNSTA multi-tenant SaaS on AWS ap-south-1: GA | Platform + Engineering | 5 clients on SaaS tier |
| 99.9% uptime SLA: architecture can support it | Platform Team | 30-day SLA test passed |
| Self-serve client onboarding flow live | Engineering | First self-onboarded client |
| DPDP Act 2023: full compliance | Engineering + Legal | Legal sign-off |
| Penetration test completed; findings remediated | CTO + Security | Clean pen test report |
| ML credit scoring: full production (non-shadow) | AI/ML Team | 1 NBFC client using ML scores for approvals |
| Developer portal Phase 1: internal | Platform Team | All engineers use Backstage for service catalog |
| Test automation: 80% coverage | QA CoE | DORA change failure rate < 10% |
| CMMI Level 4 readiness assessment initiated | CTO | Gap assessment started |

**Board KPI targets (end of Q4 / Month 12):**
- FiNSTA SaaS: 5 clients live
- ARR: 20% above Day 1 baseline
- DORA: Elite tier on 2 of 4 metrics
- NPS: +20 points from baseline
- Compliance: All P1 regulatory gaps closed
- Team: 0 unplanned attrition in engineering leads

---

### Months 13–18 — Scale, AI & Market Expansion

**Theme:** Grow the client base. AI in production. Enter new geographies.

| Milestone | Owner | Success metric |
|-----------|-------|----------------|
| ML-based credit scoring: full production rollout | AI/ML Team | All participating NBFC clients using ML scores |
| LLM document parsing: loan application automation | AI/ML Team | 60% reduction in manual data entry for pilot clients |
| Geographic expansion: Tamil Nadu sales motion active | Sales | 3 Tamil Nadu NBFC clients in pipeline |
| Geographic expansion: Maharashtra sales motion active | Sales | 3 Maharashtra NBFC clients in pipeline |
| EasyCHIT SaaS launch | Engineering | EasyCHIT on same SaaS infrastructure |
| Embedded finance API (Kapil Group internal) | Engineering | 3 Group entities using FiNSTA API |
| Developer portal Phase 2: NBFC client-facing | Platform Team | Clients self-integrating via API portal |
| CMMI Level 4 assessment: submitted | CTO | Formal submission to CMMI Institute |
| Collections module v2: ML-powered prioritisation | AI/ML + Lending Team | Collections recovery rate improved vs. v1 |

**Board KPI targets (end of Month 18):**
- Active NBFC client base: +50% from Day 1 baseline
- ARR: +40% from Day 1 baseline (confirm with finance baseline)
- DORA: Elite tier on all 4 metrics
- Developer productivity: 40% reduction in lead time vs. Day 1 baseline
- Team size: engineering headcount scaled per hiring plan

---

## Investment Summary (18 months)

> All figures are estimates pending budget confirmation with founders/finance.

| Investment category | Estimated amount (18 months) |
|--------------------|------------------------------|
| Engineering hiring (4–8 new roles) | ₹1.5–2.5 crore |
| L&D and certifications | ₹75–90 lakh |
| AWS infrastructure | ₹40–80 lakh (scales with clients) |
| Tooling (GitHub Enterprise, SonarQube, PagerDuty, Copilot, etc.) | ₹25–35 lakh |
| Compliance consultancy (DPDP, pen testing) | ₹20–30 lakh |
| **Total estimated investment** | **₹3.1–4.4 crore** |

> ROI case: Every 10% increase in NBFC client base at ₹15–40 lakh/year ARR per enterprise client represents ₹1.5–4 crore additional ARR. The investment pays back at <50% client base growth.

---

## Risk Register

| Risk | Likelihood | Impact | Mitigation |
|------|-----------|--------|------------|
| Key engineering talent exits during transition | Medium | High | Retention plan; comp review in Month 1; team topology reduces bus factor |
| Compliance deadline missed (DPDP Act) | Low | Critical | Legal priority tracking; compliance team formed in Q1 |
| AWS migration causes client disruption | Medium | High | Parallel run 3 months before cutover; opt-in migration with support |
| ML model rejected by NBFC clients | Low | Medium | Shadow mode first; SHAP explainability; human override always available |
| Roadmap scope exceeds team capacity | High | High | Ruthless prioritisation; P1 compliance and core product first; delay P3 items |
| Competitive response from Finflux/TechFini | Medium | Medium | First-mover on AA framework is 6-month window; move fast on Q2 compliance launch |

---

*Back to [90-Day Plan](../08-90-day-plan/90-day-plan.md) | Back to [README](../README.md)*
