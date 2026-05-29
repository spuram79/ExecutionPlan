# 90-Day CTO Execution Plan

## Guiding Principles

1. **Days 1–30: Listen first, change nothing.** Build trust with the team. Establish baselines. No architectural decisions until the full picture is clear.
2. **Days 31–60: Quick wins that matter.** Tackle the active signals (QA remediation, library RFP). Demonstrate CTO impact without disrupting delivery.
3. **Days 61–90: Foundations for transformation.** Structural changes begin. Board report delivered. 18-month roadmap locked.

---

## Phase 1: Discover & Baseline (Days 1–30)

### Week 1 — People first

| Day | Action | Output |
|-----|--------|--------|
| 1 | Meet founders/board — understand their vision, concerns, and definition of success for this role | CTO mandate clarity |
| 1 | Meet HR — get engineering org chart, headcount by role, attrition data | Org baseline |
| 2–3 | 1:1s with all engineering leads (backend, frontend, mobile, QA) | Team dynamics, current pain points |
| 2–3 | 1:1s with product managers / business analysts | Product roadmap context |
| 3 | Distribute skills matrix survey to all engineers | Skills baseline data |
| 4 | Meet legal/compliance team — request last audit report and compliance status | Regulatory exposure |
| 4 | Meet sales lead — understand client pipeline, recent wins/losses | GTM context |
| 5 | First all-hands with engineering team — introduce yourself, share listening intent, ask what's broken | Team trust |
| 5 | Request exports: CRM (clients), finance (ARR per product), HR (headcount) | Data foundation |

---

### Week 2 — Systems and codebase

| Day | Action | Output |
|-----|--------|--------|
| 8 | Full FiNSTA codebase walk-through with lead architects | Architecture map |
| 9 | Review CI/CD setup — does one exist? What tools, what coverage? | DevOps baseline |
| 10 | Pull deployment history: last 12 months of release logs | DORA data (manual) |
| 11 | Review open bug backlog — age, severity, distribution across modules | Quality baseline |
| 12 | Extract skills survey results — identify top 3 skill gaps | L&D priorities |
| 12 | Meet with 3–5 NBFC clients directly (calls or visits) — "what does FiNSTA do well? What frustrates you?" | Client truth |

---

### Week 3 — Competitive and market context

| Day | Action | Output |
|-----|--------|--------|
| 15 | Hands-on trials / demos of Finflux, TechFini, Nucleus LoanVantage | Competitive gap list |
| 16 | Map FiNSTA features against RBI Digital Lending 2022 requirements | Compliance gap draft |
| 17 | Map FiNSTA against DPDP Act 2023 requirements | DPDP gap draft |
| 17 | Verify CERT-In registration status; check log retention and incident reporting setup | CERT-In gap |
| 18 | Confirm Kapil Group internal FiNSTA/EasyCHIT adoption status | Captive client opportunity |
| 19 | HR follow-up: collect skills survey data, attrition data | Validate skill gaps |

---

### Week 4 — Synthesis and board prep

| Day | Action | Output |
|-----|--------|--------|
| 22 | Draft Current State Assessment document (internal) | Foundation for Board report |
| 23 | Prioritise compliance gaps with legal team — get legal sign-off on gap severity | Compliance risk map |
| 24 | Draft 90-day execution plan Phase 2 detail (refine this document with actual data) | Phase 2 ready |
| 25 | Present Current State Assessment to founders — seek validation before Phase 2 | Founder alignment |
| 26–28 | Collect any remaining discovery data; close open `[REQUIRES INTERNAL DISCOVERY]` items | Data closure |
| 29 | Finalise hiring JDs for Phase 2 critical roles: DevOps Lead, SDET × 2, Compliance Eng Lead | Hiring ready |
| 30 | Internal retrospective: what did 30-day listening reveal that wasn't expected? | Adjusted plan |

---

## Phase 2: Quick Wins & Structural Setup (Days 31–60)

### Engineering quick wins

| Action | Owner | Timeline | Success metric |
|--------|-------|----------|----------------|
| Automate top 10 critical regression paths (loan origination, disbursement, repayment) | QA Lead + new SDET | Days 31–45 | 10 automated tests running in CI |
| Stand up GitHub Actions CI pipeline on 1 FiNSTA module (pilot) | DevOps Lead | Days 31–45 | Automated build + test on every PR |
| Complete CVE scan on all dependencies; remediate Critical + High | Engineering Lead | Days 31–45 | Zero Critical CVEs open |
| Define third-party library selection criteria (ahead of RFP) | CTO | Days 31–40 | Selection criteria document published |
| Publish CERT-In PoC designation to CERT-In | CTO + Legal | Days 31–35 | Designation letter filed |
| Begin log retention setup: 180-day retention in all environments | DevOps | Days 35–50 | Logging audit passed |

---

### Structural setup

| Action | Owner | Timeline | Output |
|--------|-------|----------|--------|
| Publish Team Topology design proposal | CTO | Days 35–45 | Org design doc for founder approval |
| Kickoff hiring for 4 critical roles | CTO + HR | Days 31–40 | JDs published, sourcing started |
| Begin 1:1 cadence with all team leads (fortnightly) | CTO | Day 31 onwards | Ongoing |
| Define engineering KPI dashboard — data sources, metrics, owners | CTO + DevOps | Days 40–55 | Dashboard live (even if baseline only) |
| Launch domain expert pairing programme (NBFC knowledge transfer) | CTO + Engineering Leads | Days 45–60 | 5+ pairing pairs active |
| Initiate DPDP Act data classification exercise | Engineering + Legal | Days 45–60 | Data inventory draft |

---

### Compliance actions (non-negotiable)

| Action | Owner | Timeline |
|--------|-------|----------|
| LSP disclosure added to FiNSTA (UI change) | Engineering | Days 31–42 |
| Grievance redressal mechanism in FiNSTA | Engineering | Days 31–50 |
| KFS generation module design + sprint kickoff | Compliance Eng Lead | Days 35–50 |
| AA framework integration design doc | Engineering Lead | Days 40–55 |

---

## Phase 3: Transformation Foundations (Days 61–90)

### Board deliverables

| Deliverable | Due | Audience |
|-------------|-----|---------|
| CTO Assessment Report v1.0 | Day 75 | Board / Founders |
| 18-month technology transformation roadmap | Day 80 | Board / Founders |
| Hiring plan + investment ask (capex/opex) | Day 80 | Board / Founders |
| Engineering KPI dashboard (live) | Day 75 | Board (monthly thereafter) |

---

### Structural changes

| Action | Owner | Timeline |
|--------|-------|----------|
| Team topology go-live: stream-aligned teams formed | CTO + HR | Days 61–80 |
| Platform team formed and operational | CTO + DevOps Lead | Days 61–75 |
| QA CoE established; QA Lead named | CTO | Days 61–70 |
| CI/CD pipeline rolled out to all FiNSTA modules | Platform Team | Days 61–90 |
| 50% critical path test automation coverage achieved | QA CoE | Day 90 |
| AWS ap-south-1 proof of concept environment live | Platform Team | Days 75–90 |
| GitHub Copilot pilot launched (all engineers) | Platform Team | Days 65–70 |

---

### Communication plan

| Audience | Cadence | Format | Topics |
|----------|---------|--------|--------|
| Founders / Board | Monthly | Written report + 30-min call | DORA metrics, roadmap progress, risks |
| Engineering leads | Weekly | 45-min standup | Blockers, hiring, delivery status |
| All engineering | Fortnightly | All-hands (30 min) | Wins, roadmap updates, skill topics |
| NBFC clients (key accounts) | Monthly | Client success call | Feature roadmap, compliance updates |
| HR | Weekly | 15-min sync | Hiring pipeline, attrition risk |

---

## 90-Day Success Metrics

By Day 90, these outcomes define a successful first 90 days:

| Metric | Target |
|--------|--------|
| Board report delivered | ✅ v1.0 delivered and approved |
| DORA baseline established | ✅ All four metrics measured |
| Critical CVEs | Zero open |
| CERT-In PoC | Designated and filed |
| RBI DL 2022 quick fixes (LSP, grievance) | Live in FiNSTA |
| Test automation coverage | 20% on critical paths |
| CI/CD pipeline | Live on all modules |
| Team topology | Implemented |
| Skills survey | 100% completion |
| Hiring pipeline | 4 critical roles in process |
| Client NPS | Measured (baseline) |

---

*Back to [README](../README.md) | Next: [18-Month Roadmap →](../09-18-month-roadmap/transformation-roadmap.md)*
