# Developer Productivity Framework

## DORA Metrics — Baseline & Targets

The four DORA metrics are the industry standard for measuring engineering delivery performance. Establish baselines in Days 1–30, then track monthly.

| Metric | Definition | How to measure | Current (baseline) | Target (12 months) | Elite benchmark |
|--------|-----------|---------------|-------------------|-------------------|-----------------|
| Deployment frequency | How often code is deployed to production | CI/CD pipeline logs or release history | `[DISCOVER]` | Weekly | On-demand (multiple/day) |
| Lead time for changes | Time from code commit to running in production | Git commit timestamp → deployment timestamp | `[DISCOVER]` | < 1 week | < 1 hour |
| Change failure rate | % of deployments causing production failures | Incidents / total deployments | `[DISCOVER]` | < 10% | < 5% |
| Mean time to restore | Time to recover from production failure | Incident open → resolved timestamp | `[DISCOVER]` | < 4 hours | < 1 hour |

### How to instrument DORA today (if no CI/CD exists)
If formal CI/CD is absent, manually collect baseline data:
- Deployment frequency: count release notes / change log entries in last 3 months
- Lead time: pick 5 recent features; estimate commit-to-production time from git log
- Change failure rate: count production incidents in last 6 months / total releases
- MTTR: pull incident tickets from support/ITSM system; calculate open→resolve duration

---

## CI/CD Pipeline Implementation Roadmap

### Target pipeline architecture
```
Developer pushes code
        ↓
  [Pre-commit hooks]
  Lint + unit tests
        ↓
  [Pull Request CI]
  Build → Unit tests → Integration tests → SonarQube quality gate → Security scan (Snyk)
        ↓
  [Merge to main]
  Full test suite → Build artifact → Deploy to staging
        ↓
  [Staging environment]
  E2E tests (Playwright) → Performance tests → Manual QA sign-off
        ↓
  [Production deploy]
  Feature flag controlled rollout → Canary (10% traffic) → Full rollout
        ↓
  [Post-deploy]
  Smoke tests → Monitoring alerts → DORA metric update
```

### Implementation phases

| Phase | Actions | Timeline | Tooling |
|-------|---------|----------|---------|
| Phase 1: Foundation | GitHub Actions pipeline on 1 module (pilot) | Month 1–2 | GitHub Actions |
| Phase 2: Expand | Rollout CI pipeline to all modules; add SonarQube | Month 2–3 | SonarQube, Snyk |
| Phase 3: CD | Automated staging deployments; feature flags | Month 3–4 | LaunchDarkly/Unleash, Terraform |
| Phase 4: Production | Canary deployments to production; full DORA instrumentation | Month 5–6 | AWS CodeDeploy or ArgoCD |

---

## Developer Experience Improvements

### Local development environment
**Current likely state:** Manual setup, inconsistent environments, "works on my machine" issues  
`[REQUIRES INTERNAL DISCOVERY — ask: how long does it take a new engineer to make their first commit?]`

**Target state:**
- Containerised local dev environment (Docker Compose) — standardised across all engineers
- One-command setup: `make dev-setup` bootstraps everything
- Documented in README — tested by every new hire

### Code review standards
**Target:** Max 24-hour PR review SLA for all pull requests

| Standard | Current | Target |
|---------|---------|--------|
| PR size | Unknown | Max 400 lines changed |
| Review SLA | Unknown | 24 hours |
| Approval requirement | Unknown | Minimum 1 peer + 1 lead for core modules |
| Automated quality gates | Unknown | SonarQube + Snyk must pass before merge |
| Branch strategy | Unknown | Trunk-based development |

### Observability stack
**Target:** Every production issue detected by monitoring before a client reports it

| Layer | Tool | Purpose |
|-------|------|---------|
| Application logs | ELK Stack (Elasticsearch, Logstash, Kibana) or CloudWatch Logs | Centralised logging, 180-day retention (CERT-In compliance) |
| Metrics | Prometheus + Grafana or CloudWatch Metrics | System and business metrics |
| Distributed tracing | AWS X-Ray or Jaeger | Trace loan flow across services |
| Alerting | PagerDuty or OpsGenie | On-call rotation, escalation |
| Uptime monitoring | AWS CloudWatch Synthetics | SLA monitoring for NBFC clients |

---

## On-Call & Incident Response

FiNSTA serves live financial institutions. Downtime has regulatory and commercial impact — NBFC clients may have SLA requirements themselves.

### Incident severity matrix
| Severity | Definition | Response time | Escalation |
|----------|-----------|--------------|------------|
| P1 — Critical | FiNSTA completely down for 1+ clients | 15 minutes | Immediate to CTO |
| P2 — High | Core loan flow broken; workaround exists | 1 hour | Engineering Lead |
| P3 — Medium | Non-critical feature broken | 4 hours | Team Lead |
| P4 — Low | Minor UI bug; no business impact | Next sprint | Product backlog |

### Incident response process
1. Detect (monitoring alert or client report)
2. Acknowledge (on-call engineer via PagerDuty — 15-min SLA for P1)
3. Triage (assess severity, assemble response team)
4. Communicate (notify affected NBFC clients within 30 min for P1/P2)
5. Resolve
6. Post-mortem (blameless, within 48 hours of P1 resolution)
7. CERT-In notification (if security incident — 6-hour deadline from detection)

### On-call rotation design
- Minimum 4 engineers in rotation (no single point of failure)
- Max 1 week on-call per rotation
- On-call shadowing for first 2 rotations for new engineers
- On-call compensation policy: `[REQUIRES HR DECISION]`

---

## Engineering KPI Dashboard

Publish this dashboard to the Board monthly. Track quarterly trends.

| KPI | Measurement | Target | Board threshold |
|-----|-------------|--------|-----------------|
| Deployment frequency | Deployments per week | Weekly | < Monthly = 🔴 |
| Lead time | Days commit → production | < 5 days | > 14 days = 🔴 |
| Change failure rate | % deployments causing incidents | < 10% | > 20% = 🔴 |
| MTTR | Hours to restore production | < 4 hours | > 24 hours = 🔴 |
| Test automation coverage | % automated test coverage | 80% (Month 12) | < 50% = 🟡 |
| Bug escape rate | % bugs found in production (not QA) | < 5% | > 15% = 🔴 |
| PR cycle time | Hours from PR open to merge | < 24 hours | > 72 hours = 🟡 |
| On-call incident count | P1+P2 incidents per month | Declining trend | Increasing trend = 🔴 |

---

*Back to [Team Topology](./team-topology.md) | Back to [README](../README.md)*
