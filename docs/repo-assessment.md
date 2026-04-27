# Repo Assessment - pedigree4

*Honest evaluation of what's built and what's needed*
*Assessed: April 27, 2026 | Repo: github.com/mattrob333/pedigree4*

---

## Summary

The repository contains a solid demo-ready MVP scaffold. It is not production software. The architecture is well-designed, the documentation is thorough, and the demo system can credibly represent the Pedigree product to a Wesco team or an investor. What's missing is the production plumbing: real HRIS connectors, persistent storage, multi-tenancy, and a handful of critical security fixes.

**Bottom line:** 6-8 weeks of focused engineering to a credible Wesco PoC. 4-5 months to v1.0 production-ready.

---

## What's Built

### Backend (FastAPI / Python)
- **Human management:** List, filter, get by ID - with HRIS status, manager chain, entitlements
- **Agent management:** List, filter by status/platform, get by ID - with parent attribution
- **Policy engine:** Orphan blocking, SoD check (basic), scope enforcement (basic)
- **Runtime evaluation:** `/runtime/evaluate` endpoint - checks tool calls against parent scope
- **Cascade planning:** Termination webhook -> walk agent subtree -> plan cascade deprovision
- **Audit events:** Append-only audit log, queryable by entity
- **Demo summary:** Aggregated demo data endpoint for the UI
- **Mock Microsoft service:** Dataverse OData API + Graph API endpoints with test fixtures

### Frontend (React / Vite / TypeScript)
- Working app at `app.html` backed by the live FastAPI backend
- Humans list, agents list, cascade simulation
- Static marketing prototype at `index.html`
- Clickable product prototype at `demo.html` (preserved from earlier design phase)

### Infrastructure
- Docker Compose demo stack: API + Mock Microsoft + Neo4j + Postgres + Redis + Frontend
- GitHub Actions CI: Ruff lint, pytest smoke tests, TypeScript typecheck, Vite build, compose validation
- Neo4j graph constraints + Postgres DDL stubs
- Full OpenAPI spec (openapi.yaml)

### Documentation
- MVP PRD with epics and user stories
- High-Level Architecture
- Data Model & Schema
- Microsoft Copilot Studio Integration Spec
- Core API Spec (human-readable)
- Security Threat Model
- 90-Day Roadmap
- Implementation Backlog
- Code Review Findings

---

## Critical Gaps (Must Fix Before Wesco PoC)

### Security Issues (Fix Immediately)

| ID | Issue | Fix |
|---|---|---|
| BE-01 | Hardcoded Neo4j password in source | Read from env var, never commit credentials |
| BE-02 | Plaintext DB credentials in settings.py | Require env var, fail loudly if unset in non-demo mode |
| BE-07 | HRIS termination webhook has no auth | Require HMAC signature or bearer token before acting |
| BE-06 | CORS allows `methods=["*"]` | Restrict to required verbs and explicit headers |

**These must be fixed before any external demo or investor technical review.**

### Production Blockers (Fix Before v1.0)

| Issue | Description |
|---|---|
| No real HRIS connectors | Currently using seed fixtures - need live Workday/UKG REST + webhook integration |
| No real Entra connector | Mock Microsoft service needs replacement with production Graph API + Entra Agent ID |
| In-memory store only | Demo uses an in-memory data store - Postgres + Neo4j schemas exist but aren't wired |
| No multi-tenancy enforcement | DB schema has tenant table but tenant isolation isn't enforced at the API layer |
| Frontend not production-ready | Running Vite dev server in Docker; needs multi-stage build for production |

### Demo-Blocking Issues (Fix Before Wesco Demo)

| ID | Issue |
|---|---|
| FE-01 | demo.html not in Rollup build - won't load in production build |
| FE-02 | Silent fallback to localhost if VITE_API_URL unset |
| BE-03 | StopIteration error if policy type missing - silent 500 |

---

## What's Strong

### Architecture
The 5-layer architecture is well-conceived and the separation of concerns is clean. The graph model (Neo4j for lineage, Postgres for relational data) is the right choice for this problem. The API design is thoughtful - the OpenAPI spec is complete and correct.

### Documentation
The documentation set is exceptional for an early-stage project. The PRD has real user stories with acceptance criteria. The architecture doc explains the system clearly. The threat model is genuinely useful. This documentation package is investor-ready as-is.

### The Demo Story
The cascade deprovision demo is compelling. Simulating a Workday termination event and watching the agent subtree cascade is the "aha" moment. The demo can communicate the value proposition better than any slide.

### The Test Coverage
Smoke tests cover the three most critical paths: seed loading, orphan-policy blocking, and cascade planning. These are the right three tests to have. CI catches regressions on push.

---

## Engineering Estimate

### To Wesco PoC (6-8 weeks, 2 engineers)
- Week 1-2: Critical security fixes + demo-blocking bugs
- Week 3-4: Real Workday connector (read-only, REST + webhook)
- Week 5-6: Real Entra connector (Graph API, agent inventory)
- Week 7-8: Persistent storage (wire Postgres + Neo4j), demo polish, Wesco demo prep

### To v1.0 Production (4-5 months, 3 engineers)
- Month 1-2: Multi-tenancy, production auth, performance testing
- Month 3: App Owner Console UI (full feature set)
- Month 4: Runtime MCP gateway (replace /evaluate stub)
- Month 5: SoD/DLP engine, SOX/HIPAA audit bundle export, security audit

---

## The Honest Summary for Investors

This is exactly the right amount of code for the stage. The architecture is designed correctly, the documentation reflects real product thinking, and the demo is compelling. The gaps are well-understood and addressable engineering problems - not research problems.

The team that built this understood the problem deeply and made the right design choices. What's needed now is focused execution on the production plumbing.

---

*Full code: [github.com/mattrob333/pedigree4](https://github.com/mattrob333/pedigree4)*
*Code review findings: [docs/delivery/CODE_REVIEW_FINDINGS.md](https://github.com/mattrob333/pedigree4/blob/main/docs/delivery/CODE_REVIEW_FINDINGS.md)*
