# Pedigree - Investor Research & Market Analysis
*Prepared: 2026-04-27 | For: Seed/Series A Fundraising*

---

## The Thesis in One Sentence

Pedigree is the **platform-agnostic human-agent lineage layer** - the governance primitive that every enterprise needs regardless of whether they run Microsoft, AWS, Google, Salesforce, or custom AI agents. We don't compete with the hyperscalers; we complete them.

---

## Why This Moment

### The Convergence That Created the Gap

Three things happened simultaneously in 2025-2026 that created a governance vacuum no hyperscaler can fill:

1. **Agent proliferation hit escape velocity.** NHIs (non-human identities) now outnumber humans 25-100x at Fortune 500 enterprises. Agents created by Copilot Studio, LangChain, n8n, Zapier, and custom builds are being deployed faster than any governance team can track.

2. **The hyperscalers built identity infrastructure, not governance.** Microsoft Entra Agent ID gives agents a managed identity. AWS Agent Registry catalogs them. Google Cloud API Registry lists tools. **None of them answer the questions that keep CISOs awake:**
   - Who is the *human* responsible when this agent takes a bad action?
   - What happens to this agent when that human leaves the company?
   - Did this agent inherit scope from someone who was promoted 6 months ago and now has too much access?

3. **Compliance mandates arrived.** SOX, HIPAA, and GDPR regulators are starting to ask about AI agent audit trails. The "we're still figuring it out" answer has an expiration date.

### The Market Numbers

- **NHI Access Management market:** $12.2B in 2026 -> $38.8B by 2036 (CAGR ~12%)
- **Only 10% of enterprises** have a clear strategy to manage AI agents (Fortune/Okta, April 2026)
- **91% of organizations** are already using AI agents; only 22% treat them as independent identities (Gravitee, 2026)
- **92% of security leaders** say legacy IAM wasn't built for this problem
- Gartner's 2026 IAM Predictions: identity visibility for NHIs is "no longer optional"

---

## The Platform-Agnostic Attack Vector: Why We Win

### The Mistake Incumbents Are Making

Every hyperscaler is building governance for *their own* agents:

- Microsoft Agent 365 ($15/user/month) governs Copilot Studio and Entra Agent ID workloads well. It's weak on non-Microsoft agents.
- AWS Agent Registry catalogs Bedrock AgentCore workloads. No HRIS. No human lineage.
- Google Cloud API Registry is tool-focused, developer-centric, not enterprise governance.
- Veza (now ServiceNow) does access graph and human mapping - no HR cascade, no scope inheritance.

**The enterprise reality:** Large companies don't run one cloud. They run Microsoft *and* Salesforce *and* custom Python agents *and* n8n workflows *and* Copilot Studio *and* AWS Bedrock. They need governance that spans all of it.

### Our Position: The Layer Above the Stack

```
┌──────────────────────────────────────────────────────────────────┐
│                    PEDIGREE                                        │
│         Platform-Agnostic Human-Agent Lineage Layer               │
│  (works with any agent, any cloud, any identity provider)         │
└───────────────────────────────────────────────────────────────────┘
         ↕                    ↕                    ↕
   Microsoft Entra      AWS Bedrock           Salesforce
   Agent ID + 365       AgentCore            Einstein AI
   Copilot Studio       Lambda               Custom Agents
         ↕                    ↕                    ↕
┌──────────────────────────────────────────────────────────────────┐
│                    HRIS (Workday / UKG / ADP)                     │
│              The Ground Truth for Human Identity                   │
└───────────────────────────────────────────────────────────────────┘
```

Pedigree is the translation layer between the HRIS org chart (the one true source of human identity) and every agent platform. We don't replace Entra. We make Entra's governance complete. We don't compete with ServiceNow/Veza. We give their graph a human backbone.

### The Moat: HRIS as Source of Truth

The key architectural bet: **the HRIS org chart is the only authoritative source of human identity that spans every enterprise system.** Workday, UKG, and ADP are the systems of record for who works at the company, what their role is, who their manager is, and when they leave.

Every other identity system (Entra, Okta, Ping) is downstream of HR. Every agent platform (Copilot Studio, Bedrock, LangChain) is downstream of Entra/Okta.

Pedigree sits at the root: wire every agent to the HRIS org chart, and cascade deprovision, scope inheritance, SoD enforcement, and audit trails all fall out as consequences of that single design decision.

Once a customer's HRIS is wired and their agent fleet is mapped, the lineage graph becomes load-bearing infrastructure. Ripping it out means rebuilding years of lineage history and re-certifying thousands of agents manually. **The moat is the graph.**

---

## Why We Can Win Against Microsoft Specifically

This is the most important investor question. Here's the honest answer:

**Microsoft is building a great identity layer. They are not building a governance layer.**

| Capability | Entra Agent ID + Agent 365 | Pedigree |
|---|---|---|
| Agent identity (who is this agent?) | ✅ Best in class | Uses Entra as foundation |
| Agent inventory | ✅ Good for M365/Copilot agents | All agents, all platforms |
| Ownership metadata | Partial (owner field, no HR validation) | HRIS-verified human parent |
| Org chart lineage | ❌ No parent-child graph | ✅ Core feature |
| HR-driven lifecycle | ❌ No Workday/UKG connector | ✅ Core feature |
| Cascade deprovision on termination | ❌ Manual process | ✅ Automated in <60s |
| Scope inheritance (strict subset) | ❌ Not implemented | ✅ OAuth 2.1 Token Exchange |
| SoD enforcement in org terms | ❌ Not implemented | ✅ Policy engine |
| Non-Microsoft agent support | Limited | ✅ All agents |
| App owner console | ❌ | ✅ Core feature |

**The positioning:** "Entra tells you *who* the agent is. Pedigree tells you *why* it exists, *what* it can do forever, and *what happens when the human leaves.*"

We are a **governance layer on top of Entra, not a competitor to it.** Every Microsoft-heavy enterprise that buys Agent 365 will still have the orphan problem, the scope inheritance problem, and the HR termination gap. Pedigree solves those.

**The partnership play, not the war:** Microsoft's Partner Network is how we enter enterprise accounts. "Pedigree-certified for Entra Agent ID" is a credible enterprise GTM motion that doesn't require us to fight the $3T company.

---

## The "Why Now" Wedge: 3 Timing Factors

**1. Microsoft just created the vacuum.** Entra Agent ID + Agent 365 launches at $15/user/month. Every enterprise that evaluates it will immediately ask: "What about our non-Microsoft agents? What about the HRIS integration? What about agents owned by people who left?" Pedigree answers all three. The best time to sell a complement is when the category is being defined.

**2. The ServiceNow/Veza acquisition creates churn.** Veza customers are uncertain about their roadmap. ServiceNow is absorbing them into a $150B platform. There is a 12-18 month window where CISOs who were evaluating Veza are reconsidering. Pedigree enters with a sharper, more specific story.

**3. Compliance deadlines are real.** The SOX audit season is coming. The HIPAA enforcement actions on AI are coming. "We're figuring it out" stops working when the auditor shows up and asks who owns the agent that accessed patient records last Tuesday at 2am.

---

## Repo Assessment: What's Built, What's Needed

### What's Actually in the Repo (Honest)

**Strong foundation:**
- FastAPI backend with working endpoints for humans, agents, policies, runtime evaluation, HRIS termination cascade planning, and audit events
- Mock Microsoft service (Dataverse + Graph) for realistic demo
- Neo4j graph constraints + Postgres DDL stubs
- Working React UI backed by the live API
- Demo seed data (HRIS employees, Dataverse bots, resources)
- Smoke tests covering seed loading, orphan-policy blocking, cascade planning
- Full documentation set: PRD, architecture spec, data model, API spec, security threat model, 90-day roadmap, GTM positioning
- Docker Compose demo stack (API + mock Microsoft + Neo4j + Postgres + Redis + frontend)
- CI/CD (GitHub Actions: lint, typecheck, build, compose validation)

**This is a credible demo-ready MVP scaffold.** It can demonstrate the core value proposition to Wesco and early investors.

### What's Missing for Production (Honest)

**Critical gaps before real enterprise deployment:**
1. **Real HRIS connectors** - currently uses seed fixtures; needs live Workday/UKG REST + webhook integration
2. **Real Entra connector** - mock Microsoft service needs replacement with production Graph API + Entra Agent ID integration
3. **Persistent storage** - currently in-memory; Postgres + Neo4j schemas exist but aren't wired
4. **Runtime MCP gateway** - the `/runtime/evaluate` endpoint is MVP; the MCP-aware inline gateway is the production version (v1.1)
5. **Multi-tenancy** - DB schema has tenant table but isolation isn't enforced
6. **Auth on webhooks** - the HRIS termination webhook has no auth (critical security issue, documented in code review)
7. **Production hardening** - ~40 code review findings, including 2 critical security issues (hardcoded credentials in source)

**Honest estimate for Wesco PoC readiness:** 6-8 weeks of focused engineering to close the critical gaps and stand up a live integration with their Workday + Entra environment.

**Honest estimate for v1.0 production:** 4-5 months with a small team (2-3 engineers).

### What the Code Review Reveals

The code review found 40+ findings across backend, frontend, infra, and docs. The two most important:
- **BE-01/BE-02:** Hardcoded credentials in source (needs immediate fix before any external demo)
- **BE-07:** Termination webhook has no auth (anyone can trigger cascade - critical)
- **FE-01:** `demo.html` not bundled in production build (demo won't work in prod)

These are fixable in a sprint. They don't reflect on the architecture - they reflect on early-stage development velocity.

---

## Go-to-Market: Speed-First Motion

### Land: The Orphan List as a Trojan Horse

**Free tier:** Connect HRIS + Entra -> generate the "Orphan List" in 48 hours.

Every enterprise has orphaned agents - agents still active with live credentials, owned by people who left months ago. The Orphan List is the single most visceral demo in security. When the CISO sees 47 active agents owned by departed employees, Pedigree sells itself.

The Orphan List is free. The platform that cleans it up and prevents it from happening again is paid.

### Expand: Per-Agent Pricing

- **Discovery tier (free):** HRIS sync + Entra inventory + Orphan List
- **Core ($75-100/agent/month):** Parent assignment, scope enforcement, lifecycle automation
- **Enterprise ($150-200/agent/month):** Runtime gateway, SoD engine, DLP, dedicated support, custom HRIS connectors

Expected: 500-5,000 agents per F500 customer within 18 months of deployment.

**Example unit economics at scale:**
- 1,000 agents x $100/month = $1.2M ARR per customer
- 10 enterprise customers = $12M ARR
- Enterprise contract ranges: $500K-$2M ARR

### Wesco as Launch Partner

Wesco International / Anixter (Fortune 500) has already articulated the exact 8-gap spec that Pedigree addresses. They are blocking Copilot Studio deployment until governance exists. This is the design partner PoC - success here is both category proof and the first reference customer story.

**The Wesco PoC plan:**
- 90 days to live graph + basic runtime with their Workday + Entra environment
- Success metric: demonstrate cascade deprovision on a simulated termination event
- Output: a case study that unlocks the next 5 enterprise customers

---

## Competitive Moat Summary

| Competitor | Their angle | Pedigree's edge |
|---|---|---|
| Microsoft Entra Agent ID + 365 | Identity-first, M365-centric | HRIS lineage, HR cascade, non-MSFT agents, platform-agnostic |
| ServiceNow + Veza | Discovery + access graph | Strict scope inheritance, HR lifecycle, app owner console |
| Britive / PlainID | JIT/ZSP runtime | Policy source of truth, long-term ownership, deprovision story |
| AWS Agent Registry | Cloud-agnostic catalog | Human lineage, HR events, governance (not just discovery) |
| Astrix Security | Agent discovery, policy enforcement | Deep HRIS integration, scope inheritance, lifecycle |

**What nobody has:** The authoritative human-to-agent lineage graph wired to HRIS with cascade deprovision. This is Pedigree's single unique primitive.

---

## The Investor Narrative: Platform Complement, Not Platform Competitor

**The Okta parallel:** Okta didn't compete with Active Directory - it made AD usable across cloud apps. It became the identity layer that every SaaS app integrated with. $17B market cap.

**The Snowflake parallel:** Snowflake didn't compete with data warehouses - it became the cross-cloud data layer that sat above them all. $50B+ market cap at peak.

**Pedigree's parallel:** We don't compete with Entra or ServiceNow or AWS. We become the cross-platform governance layer that every enterprise needs regardless of which agent platforms they run. The HRIS org chart is already universal - we make it the universal governance primitive for AI agents.

**The bet:** Agent governance becomes a $5-10B standalone market, won by whoever owns the authoritative human-agent lineage graph. That graph has to be HRIS-native, platform-agnostic, and hard to rip out. That's Pedigree.

---

## Market Research Sources

1. NHI Access Management Market: $12.2B (2026) -> $38.8B (2036) - Yahoo Finance / Market Research
2. 91% of orgs using AI agents; only 10% have a governance strategy - Fortune / Okta, April 2026
3. 22% of organizations treat AI agents as independent identities - Gravitee, 2026
4. ServiceNow acquires Veza for $1B - December 2025 (validates category)
5. Microsoft Agent 365 GA at $15/user/month - May 2026
6. AWS Agent Registry preview - AgentCore, April 2026
7. Gartner 2026 IAM Predictions: NHI visibility "no longer optional"
8. Forbes: "Agent Registries Become The New Battleground For Cloud Giants" - April 2026
9. Strata.io: Only 23% of organizations have formal enterprise-wide agent identity strategy - 2026
