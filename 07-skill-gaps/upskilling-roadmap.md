# Upskilling Roadmap & L&D Plan

## Certification Tracks (Team Leads & Seniors)

Prioritise in order. Target one certification per lead per 6 months.

| Certification | Provider | Target role | Timeline | Estimated cost |
|--------------|---------|------------|----------|----------------|
| AWS Solutions Architect — Associate | AWS | Tech Leads, DevOps | Month 2–4 | ~$300 per person |
| AWS DevOps Engineer — Professional | AWS | Platform/DevOps Lead | Month 4–6 | ~$300 |
| Certified Kubernetes Administrator (CKA) | CNCF | Platform Engineer | Month 5–7 | ~$395 |
| ISTQB Advanced — Test Manager | ISTQB | QA Lead | Month 2–4 | ~₹15,000 |
| Google ML Crash Course → TF Developer Cert | Google | ML Engineer | Month 3–6 | Free + ~$100 |
| CDPSE (Certified Data Privacy Solutions Engineer) | ISACA | Compliance Lead | Month 4–8 | ~$575 |
| FinTech Regulation Certificate | IIM / IIBF | Compliance Engineering Lead | Month 3–6 | ~₹20,000 |

---

## In-House Training Programme

### Track 1: Cloud & DevOps Fundamentals (All Engineers)
**Duration:** 8 weeks, 2 hours/week  
**Format:** Internal workshop led by Platform Lead + external course (A Cloud Guru / Udemy)

| Week | Topic |
|------|-------|
| 1 | Cloud fundamentals: AWS core services (EC2, S3, RDS, IAM) |
| 2 | Containerisation: Docker hands-on with FiNSTA codebase |
| 3 | Docker Compose for local development |
| 4 | CI/CD fundamentals: GitHub Actions walkthrough |
| 5 | Infrastructure as Code: Terraform basics |
| 6 | Monitoring and observability: CloudWatch + Grafana |
| 7 | AWS security fundamentals (for DPDP and CERT-In compliance) |
| 8 | Capstone: deploy a FiNSTA module end-to-end on AWS |

---

### Track 2: Test Automation (QA + Backend Engineers)
**Duration:** 6 weeks, 2 hours/week  
**Format:** Internal QA CoE workshop; hands-on with FiNSTA test scenarios

| Week | Topic |
|------|-------|
| 1 | Test automation strategy: the test pyramid for FiNSTA |
| 2 | Unit testing: JUnit/Jest — writing testable code |
| 3 | API testing: REST Assured + contract testing with Pact |
| 4 | UI automation: Playwright setup on FiNSTA web portal |
| 5 | CI integration: plugging tests into GitHub Actions |
| 6 | Capstone: automate the loan origination regression suite |

---

### Track 3: NBFC Regulation & Compliance (All Product-Facing Engineers)
**Duration:** 4 weeks, 1.5 hours/week  
**Format:** Compliance Lead + external NBFC legal counsel guest sessions

| Week | Topic |
|------|-------|
| 1 | RBI Master Directions for NBFCs — what matters for FiNSTA |
| 2 | RBI Digital Lending Guidelines 2022 — engineering implications |
| 3 | DPDP Act 2023 — consent management and data rights for engineers |
| 4 | CERT-In 2022 + Account Aggregator framework overview |

---

### Track 4: AI/ML for Engineers (Interested Engineers)
**Duration:** 8 weeks, 2 hours/week  
**Format:** AI/ML Enabling Team lead + Coursera / fast.ai materials

| Week | Topic |
|------|-------|
| 1–2 | ML fundamentals: supervised learning, classification, regression |
| 3–4 | Credit scoring with XGBoost: features, training, evaluation |
| 5 | Model explainability with SHAP — RBI requirement |
| 6 | MLOps: MLflow for experiment tracking and model registry |
| 7 | LLM integration: using Claude/OpenAI APIs in application code |
| 8 | Capstone: build a basic credit scoring prototype on sample NBFC data |

---

## External Learning Platforms (Team Subscriptions)

| Platform | Use case | Estimated cost/year |
|----------|---------|---------------------|
| A Cloud Guru / Pluralsight | AWS + DevOps courses | ₹8–12 lakh (team licence) |
| Coursera for Business | ML, Data Science tracks | ₹10–15 lakh (team licence) |
| IIBF e-learning | NBFC regulatory courses | ₹2–3 lakh |
| GitHub Copilot Business | AI-assisted development for all engineers | ~$19/user/month ≈ ₹4–5 lakh/year |

---

## Knowledge Preservation Plan

FiNSTA's deep NBFC domain knowledge is a competitive moat — it must be documented and transferred systematically.

### Actions
1. **Domain expert pairing program:** Each engineer with 3+ years of NBFC domain knowledge is paired with 1–2 newer engineers. Monthly knowledge transfer sessions.
2. **Internal wiki (Confluence or Notion):** Document:
   - NBFC business processes (loan origination, collections, RBI reporting)
   - FiNSTA architecture decisions (create Architecture Decision Records — ADRs)
   - Regulatory interpretation guidelines (how FiNSTA implements each RBI requirement)
3. **Recorded training sessions:** All Track 3 compliance sessions recorded and indexed
4. **Offboarding protocol:** When any senior engineer exits, require 2-week knowledge transfer with wiki documentation before last day

---

## L&D Budget Estimate

> Adjust based on final team headcount from HR discovery.

| Item | Estimated cost (annual) |
|------|------------------------|
| External certifications (15 team leads × 2 certs each) | ₹8–10 lakh |
| Team learning platform subscriptions | ₹20–28 lakh |
| GitHub Copilot (all engineers, ~50 eng) | ₹5–6 lakh |
| External training workshops (compliance, AI/ML) | ₹5–8 lakh |
| Conference sponsorship (1 engineer to AWS re:Invent or similar) | ₹3–5 lakh |
| **Total estimate** | **₹41–57 lakh/year** |

> Present to Board as part of the 18-month transformation investment ask.

---

## Skills Survey Template

Distribute this survey to all engineers in Week 1 via Google Forms or equivalent.

```
Kapil IT Solutions — Engineering Skills Assessment Survey

Name: ___________________
Role: ___________________
Years at Kapil IT: ______
Years in software engineering: ______

Rate your proficiency in each area (1 = No knowledge, 5 = Expert/can teach others):

Cloud & Infrastructure
  AWS / cloud services:                [ 1 ] [ 2 ] [ 3 ] [ 4 ] [ 5 ]
  Docker / containerisation:           [ 1 ] [ 2 ] [ 3 ] [ 4 ] [ 5 ]
  Kubernetes:                          [ 1 ] [ 2 ] [ 3 ] [ 4 ] [ 5 ]
  Terraform / IaC:                     [ 1 ] [ 2 ] [ 3 ] [ 4 ] [ 5 ]

Development Practices
  Unit and integration testing:        [ 1 ] [ 2 ] [ 3 ] [ 4 ] [ 5 ]
  UI/API test automation:              [ 1 ] [ 2 ] [ 3 ] [ 4 ] [ 5 ]
  CI/CD pipelines:                     [ 1 ] [ 2 ] [ 3 ] [ 4 ] [ 5 ]
  REST API design (OpenAPI):           [ 1 ] [ 2 ] [ 3 ] [ 4 ] [ 5 ]

Domain Knowledge
  NBFC operations and regulations:     [ 1 ] [ 2 ] [ 3 ] [ 4 ] [ 5 ]
  RBI Digital Lending Guidelines:      [ 1 ] [ 2 ] [ 3 ] [ 4 ] [ 5 ]
  DPDP Act 2023:                       [ 1 ] [ 2 ] [ 3 ] [ 4 ] [ 5 ]

Emerging Technologies
  AI/ML fundamentals:                  [ 1 ] [ 2 ] [ 3 ] [ 4 ] [ 5 ]
  LLM / GenAI integration:             [ 1 ] [ 2 ] [ 3 ] [ 4 ] [ 5 ]

Open Questions
  Which 2 skills do you most want to develop in the next 12 months?
  _______________________________________________________________

  Are there any technology areas where you feel the team is significantly weak?
  _______________________________________________________________

  What learning format works best for you? (online course / internal workshop / mentoring / conferences)
  _______________________________________________________________
```

---

*Back to [Skill Gap Matrix](./skill-gap-matrix.md) | Back to [README](../README.md)*
