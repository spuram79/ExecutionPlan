# Engineering Organisation — Team Topology Design

## Current State Assessment

> **[REQUIRES INTERNAL DISCOVERY — method: engineering leads 1:1s, Week 1]**
> - Total engineering headcount: ___
> - Current team structure: functional silos / squads / pods / other
> - Engineering attrition (last 12 months): ___%
> - Average PR cycle time: ___ hours
> - Sprint predictability (planned vs. delivered): ___%

---

## Proposed Team Topology

Based on the Team Topologies framework (Skelton & Pais), restructure around four team types to reduce cognitive load, accelerate delivery, and align to FiNSTA's value streams.

```
┌─────────────────────────────────────────────────────────────┐
│                    STREAM-ALIGNED TEAMS                     │
│                                                             │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────────┐  │
│  │   FiNSTA     │  │  Compliance  │  │   Mobile / UX    │  │
│  │   Lending    │  │  & Reporting │  │   (FiNSTA app)   │  │
│  │  (core loan  │  │  (RBI, DPDP, │  │  (iOS/Android,   │  │
│  │   lifecycle) │  │  CERT-In)    │  │   offline-first) │  │
│  └──────────────┘  └──────────────┘  └──────────────────┘  │
└─────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│                      PLATFORM TEAM                          │
│          DevOps, Infrastructure, CI/CD, Observability       │
│         (serves all stream-aligned teams)                   │
└─────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│                      ENABLING TEAMS                         │
│  ┌──────────────────────────┐  ┌───────────────────────┐   │
│  │   QA / Testing CoE       │  │   AI/ML Engineering   │   │
│  │  (automation, SDET,      │  │  (credit scoring,     │   │
│  │   shift-left QA)         │  │   document parsing,   │   │
│  │                          │  │   LLM integration)    │   │
│  └──────────────────────────┘  └───────────────────────┘   │
└─────────────────────────────────────────────────────────────┘
```

---

## Stream-Aligned Teams

### Team 1: FiNSTA Lending (Core)
**Value stream:** End-to-end loan lifecycle — origination through repayment  
**Owns:** Loan origination, credit assessment, disbursement, repayment, accounting, loan configurator, scheme configurator  
**Interfaces:** Platform team (infra), QA CoE (test automation), Compliance team (regulatory features)

| Role | Count | Notes |
|------|-------|-------|
| Engineering Lead | 1 | Owns architecture decisions for lending domain |
| Backend Engineers | 3–4 | Java/Python/Node.js (confirm stack internally) |
| Frontend Engineer | 1–2 | Web portal for NBFC loan officers |
| QA (embedded) | 1 | SDET — writes automated tests alongside feature development |

---

### Team 2: Compliance & Reporting
**Value stream:** All regulatory compliance features and RBI/audit reporting  
**Owns:** KFS generation, LSP disclosure, DPDP consent module, CERSAI automation, AA framework integration, audit reports, RBI returns  
**Interfaces:** Legal team (requirements), Platform team (infra), FiNSTA Lending (regulatory hooks)

| Role | Count | Notes |
|------|-------|-------|
| Engineering Lead | 1 | Must have strong RBI/fintech compliance knowledge |
| Backend Engineers | 2–3 | Focus: integrations (CERSAI, CIBIL, AA, UIDAI) |
| Legal/Compliance Liaison | 0.5 | Shared resource from legal team |
| QA (embedded) | 1 | Compliance testing requires domain expertise |

---

### Team 3: Mobile / UX
**Value stream:** FiNSTA mobile application — borrower and field agent experiences  
**Owns:** iOS and Android apps, offline-first loan origination, mobile UX, accessibility  
**Interfaces:** FiNSTA Lending team (API contracts), Platform team (mobile CI/CD)

| Role | Count | Notes |
|------|-------|-------|
| Mobile Lead | 1 | React Native or Flutter (decision pending) |
| Mobile Engineers | 2–3 | Cross-platform preferred |
| UX Designer | 1 | Must understand rural NBFC agent context |
| QA (embedded) | 1 | Mobile testing — device matrix, offline scenarios |

---

## Platform Team
**Mission:** Reduce toil for stream-aligned teams; provide paved road for deployment, observability, and infrastructure  
**Owns:** CI/CD pipelines (GitHub Actions), infrastructure as code (Terraform), AWS account management, monitoring (CloudWatch + Grafana), secrets management (Vault), developer portal (Backstage — Phase 2)

| Role | Count | Notes |
|------|-------|-------|
| Platform/DevOps Lead | 1 | Strong AWS + Kubernetes background |
| DevOps Engineers | 2 | IaC, pipeline automation |
| Site Reliability | 1 | On-call rotation lead, incident response |

---

## Enabling Teams

### QA / Testing Centre of Excellence (CoE)
**Mission:** Accelerate test automation adoption across all stream-aligned teams; define testing standards and frameworks  
**Owns:** Test strategy, automation frameworks selection, SDET skill development, quality KPIs

### AI/ML Engineering Enabling Team
**Mission:** Build AI/ML capabilities and integrate into FiNSTA product; upskill engineering teams on ML tooling  
**Owns:** ML model development (credit scoring), LLM integration (document parsing), MLOps pipeline, AI feature roadmap

---

## Hiring Plan (Priority Roles)

| Role | Team | Priority | Timeline | Notes |
|------|------|----------|----------|-------|
| Platform/DevOps Lead | Platform | 🔴 P1 | Month 1–2 | Critical path for CI/CD transformation |
| SDET (x2) | QA CoE | 🔴 P1 | Month 1–2 | QA remediation signal — move fast |
| Compliance Engineering Lead | Compliance | 🔴 P1 | Month 1–2 | DPDP + RBI DL 2022 remediation |
| ML Engineer | AI/ML Enabling | 🟡 P2 | Month 3–4 | Credit scoring pilot in Q3 |
| Mobile Lead (React Native/Flutter) | Mobile/UX | 🟡 P2 | Month 2–3 | Mobile UX refresh |
| UX Designer | Mobile/UX | 🟡 P2 | Month 3 | Rural NBFC UX expertise |
| DevOps Engineers (x2) | Platform | 🟡 P2 | Month 2–3 | Support platform team build-out |

---

## Interaction Modes

| Teams | Interaction mode | Cadence |
|-------|-----------------|---------|
| Stream-aligned ↔ Platform | X-as-a-Service | Platform provides paved road; stream teams consume |
| Stream-aligned ↔ QA CoE | Facilitating | QA CoE coaches, reviews, and sets standards |
| Stream-aligned ↔ AI/ML | Facilitating | ML engineers embed temporarily during feature build |
| Lending ↔ Compliance | Collaboration | Required during any RBI-impacted feature development |

---

*Back to [README](../README.md) | Next: [Developer Productivity →](./developer-productivity.md)*
