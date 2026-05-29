# Internal Discovery Checklist — Days 1–30

Use this checklist during the first 30 days to replace all `[REQUIRES INTERNAL DISCOVERY]` placeholders in this repository with verified internal data.

---

## Domain 1: FiNSTA Product & Codebase

### Data to collect
- [ ] Tech stack: programming languages, frameworks, versions in use
- [ ] Database technology and schema complexity
- [ ] Cloud/hosting: on-premise, co-located, or cloud? Which provider? Which region?
- [ ] Deployment model: how is FiNSTA delivered to clients? (Installed, hosted, SaaS?)
- [ ] Current pricing model: perpetual licence, subscription, or project-based?
- [ ] Test coverage %: total, unit, integration, E2E
- [ ] Open bug backlog count and age distribution
- [ ] Deployment frequency: how often are releases shipped?
- [ ] Mean time to restore (MTTR): last 12 months
- [ ] Active NBFC client count
- [ ] Client churn rate (last 12 months)

### How to collect
| Data point | Method |
|-----------|--------|
| Tech stack | Codebase walk-through with lead architects |
| Test coverage | CI/CD pipeline or manual test report |
| Bug backlog | Jira / Azure DevOps / GitHub Issues export |
| Deployment frequency | CI/CD pipeline logs or release history |
| Client count and churn | CRM export or finance team |

---

## Domain 2: Regulatory Compliance

### Data to collect
- [ ] Last RBI audit findings and closure status
- [ ] DPDP Act 2023 readiness self-assessment (if any exists)
- [ ] CERT-In registration and incident log (last 12 months)
- [ ] CERSAI integration: automated or manual? What is the current SLA?
- [ ] CIBIL integration: real-time API or batch? Version of API in use?
- [ ] Account Aggregator (AA) framework: any existing integration or roadmap item?
- [ ] e-KYC (Aadhaar/UIDAI): current integration status and UIDAI licence validity
- [ ] Data residency: where is client data stored? Is any data outside India?
- [ ] Last penetration test: date, vendor, findings, closure rate

### How to collect
| Data point | Method |
|-----------|--------|
| RBI audit findings | Compliance officer / legal team |
| DPDP readiness | Legal team + ISO 27001 audit records |
| CERT-In status | IT security lead |
| Third-party integrations | Lead backend architect + vendor contracts |
| Data residency | Infrastructure/DevOps team |
| Penetration test | IT security lead + vendor reports |

---

## Domain 3: Engineering Organisation

### Data to collect
- [ ] Total engineering headcount by role (backend, frontend, mobile, QA, DevOps, data)
- [ ] Team structure: squads, pods, or functional silos?
- [ ] Engineering attrition rate (last 12 months)
- [ ] On-call rotation: is there one? Who is on it?
- [ ] Incident frequency: P1/P2 incidents in last 12 months
- [ ] PR review cycle time: average time from PR open to merge
- [ ] Sprint velocity and predictability (last 6 sprints)
- [ ] Current CI/CD tooling (if any)
- [ ] Code review process: peer review, lead review, or self-merge?
- [ ] Documentation state: architecture docs, API docs, onboarding guides — do they exist?

### How to collect
| Data point | Method |
|-----------|--------|
| Headcount by role | HR system export |
| Team structure | Engineering leads 1:1s (Week 1) |
| Attrition rate | HR team |
| Incident data | Monitoring/alerting system logs |
| PR cycle time | GitHub/GitLab/Bitbucket analytics |
| Sprint data | Jira / Azure DevOps sprint reports |

---

## Domain 4: Clients & GTM

### Data to collect
- [ ] Full list of NBFC/Nidhi/MACS clients (active)
- [ ] ARR (Annual Recurring Revenue) per product line: FiNSTA, EasyCHIT, Hexabuild
- [ ] Net Promoter Score (NPS) — if measured
- [ ] Top 5 client pain points (gather directly in client interviews)
- [ ] Sales pipeline: number of deals, average deal size, average sales cycle length
- [ ] Last 5 competitive losses: which competitor won, and why?
- [ ] Geographic distribution of current client base
- [ ] Kapil Group internal adoption: which group companies use FiNSTA/EasyCHIT?

### How to collect
| Data point | Method |
|-----------|--------|
| Client list and ARR | CRM export + finance team |
| NPS | Customer success team (or conduct if not measured) |
| Client pain points | Direct client interviews (target 5 in Days 1–30) |
| Sales pipeline | CRM export + sales lead interview |
| Competitive losses | Sales team win/loss analysis |
| Group internal use | Internal stakeholder interviews |

---

## Domain 5: Skills & Team Capability

### Data to collect
- [ ] Current certifications per team member
- [ ] Training completed in last 12 months (L&D records)
- [ ] Self-assessed proficiency levels (distribute skills matrix survey — template in `assets/`)
- [ ] Technology stack engineers want to learn (gather in 1:1s)
- [ ] Any existing internal training programmes
- [ ] L&D budget for current financial year

### How to collect
| Data point | Method |
|-----------|--------|
| Certifications | HR system or direct survey |
| Training history | L&D / HR records |
| Proficiency levels | Skills matrix survey (Week 1) |
| Learning aspirations | Engineering 1:1s |
| L&D budget | HR / Finance |

---

## Week 1 Priority Actions

These five actions produce the highest discovery ROI in the first week:

1. **Distribute skills matrix survey** to all engineers (template: `assets/skills-matrix-survey.md`)
2. **Book 1:1s** with all engineering leads, product owners, and at least 2 NBFC client contacts
3. **Request exports** from HR (headcount), CRM (clients/pipeline), and finance (ARR per product)
4. **Schedule codebase walk-through** with lead architect for end of Week 2
5. **Request last compliance/audit report** from legal/compliance team

---

## Discovery Completion Tracker

| Domain | Status | Owner | Target date |
|--------|--------|-------|-------------|
| FiNSTA product & codebase | ⬜ Not started | CTO | Day 14 |
| Regulatory compliance | ⬜ Not started | CTO + Legal | Day 21 |
| Engineering organisation | ⬜ Not started | CTO | Day 10 |
| Clients & GTM | ⬜ Not started | CTO + Sales | Day 28 |
| Skills & team capability | ⬜ Not started | CTO + HR | Day 7 |

> Update this table as discovery progresses. Move to `v1.0` tag once all items are complete.

---

*Back to [README](../README.md)*
