# Investor Deck - Full Content

*12-slide structure for seed/Series A conversations*
*Prepared: April 2026*

---

## Slide 1: Title

**Headline:** Every Agent Has a Pedigree.

**Sub:** The platform-agnostic human-agent lineage layer for the enterprise.

**Visual:** Clean org chart diagram with human nodes and agent child nodes. A single terminated human node with a cascade of agent nodes going grey beneath it.

**Notes for presenter:** Lead with the concept, not the feature list. The image should communicate the thesis before you say a word.

---

## Slide 2: The Problem - Two Org Charts

**Headline:** Every enterprise has two org charts. Only one is governed.

**Left side (the known org chart):** Workday. Auditable. Tied to HR. When Sarah leaves, her access is deprovisioned. We know this. It works.

**Right side (the hidden agent org chart):** `.env` files. Scattered service accounts. Untraceable credentials. When Sarah leaves... her 14 agents keep running. Nobody knows.

**The 8 Gaps (from Wesco/Anixter validation):**
1. No ownership attribution - agents go rogue after creator departs
2. No scope enforcement - agents silently exceed creator's access
3. No SoD for agents - toxic action combinations, unchecked
4. No app-owner approval - ServiceNow, SAP, Oracle owners have no visibility
5. No lifecycle management - agents accumulate forever
6. No runtime enforcement - discovery tools exist; inline policy doesn't
7. No data exfiltration guardrails - agents scoop PII/PHI/PCI beyond scope
8. Audit trail gaps - even Copilot bypasses M365 logs in documented cases

**Notes:** The Wesco attribution is important. "Validated by a Fortune 500 Head of IAM" makes this a customer-confirmed spec, not a vendor-invented problem.

---

## Slide 3: The Market

**Headline:** $12.2 billion today. $38.8 billion by 2036. 91% have the problem. 10% have a plan.

**Key data points:**
- NHI Access Management: $12.2B (2026) -> $38.8B (2036) at ~12% CAGR
- 91% of enterprises are already using AI agents (Fortune/Okta, 2026)
- Only 10% have a governance strategy (Fortune/Okta, 2026)
- 92% of security leaders say legacy IAM wasn't built for agents
- ServiceNow acquired Veza for $1B (Dec 2025) - category validation

**Visual:** Market size bar chart + the 91%/10% stat in large format. The contrast is the story.

**Notes:** The $1B acquisition is the investor hook. When someone asks "is this real?" - $1B says yes.

---

## Slide 4: Our Thesis - The Design Choice

**Headline:** Wire every agent to the live HRIS org chart. Governance falls out.

**The single design choice:** Every AI agent is a digital child of a verified human in the org chart. Agents inherit a strict subset of the parent's entitlements. When the parent is terminated in Workday, the entire agent subtree is decommissioned in <60 seconds.

**Architecture diagram:**
```
HRIS (Workday / UKG / ADP)
    -> Human nodes with manager chains, entitlements, status
        -> Agent nodes (inherited scope, strict subset)
            -> Runtime enforcement (every tool call checked)
                -> Audit log + cascade deprovision on HR events
```

**The invariant:** Every AI agent must resolve to an active human parent in the HRIS org chart - or Pedigree explicitly marks it orphaned and produces audit evidence for remediation.

**Notes:** This is the "aha" slide. The insight is simple: the HRIS already has the right data. Pedigree makes it the governance source of truth for agents.

---

## Slide 5: The 5 Layers

**Headline:** One design decision. Five layers. All 8 gaps solved.

| Layer | What It Does | Solves Gaps |
|---|---|---|
| L1: Shadow Org Graph | HRIS sync -> human-agent graph -> cascade deprovision | 1, 5 |
| L2: Credential Clone Engine | OAuth 2.1 Token Exchange -> scoped derivative credentials | 2 |
| L3: MCP-Aware Gateway | Every tool call checked against parent scope + SoD + DLP | 3, 6, 7, 8 |
| L4: App Owner Console | System owners see agents, parent, history, one-click revoke | 4 |
| L5: SoD & DLP Engines | Toxic combo detection + data redaction in org terms | 3, 7 |

**Notes:** Keep this slide visual - a layered diagram works better than a table. The key insight: these aren't five separate products. They're one coherent architecture built on the lineage graph.

---

## Slide 6: Why We Win - Platform-Agnostic

**Headline:** We don't compete with Entra. We complete it.

**The positioning:**
> "Entra tells you *who* the agent is. Pedigree tells you *why* it exists, *what* it can do forever, and *what happens when the human leaves.*"

**The comparison table (simplified):**

| | Entra Agent 365 | ServiceNow+Veza | Pedigree |
|---|---|---|---|
| Multi-platform agents | ❌ M365 only | ✅ Discovery | ✅ All agents |
| HRIS-verified lineage | ❌ | ❌ | ✅ |
| HR cascade deprovision | ❌ Manual | ❌ | ✅ <60s |
| App owner console | ❌ | ❌ | ✅ |

**The partnership angle:** Microsoft Partner Network certification. "Pedigree-certified for Entra Agent ID." Co-sell motion - no war with the platform.

**Notes:** The Okta analogy is powerful here. "Okta didn't compete with AD. It made AD work everywhere. Pedigree doesn't compete with Entra. It makes agent governance complete."

---

## Slide 7: Why Now

**Headline:** 12-18 month window. Three factors converged.

1. **Microsoft created the vacuum.** Entra Agent ID just launched. CISOs are having the governance conversation. But Entra leaves the hardest gaps open. We walk into a warm conversation.

2. **ServiceNow/Veza acquisition creates churn.** $1B acquisition. Veza customers uncertain. 12-18 month displacement window - standard post-acquisition dynamics.

3. **Compliance deadlines are real.** SOX audit season. HIPAA enforcement on AI arriving. "We're figuring it out" stops working when the auditor shows up.

**The window will close.** Microsoft will eventually close some of these gaps. Another startup will raise $20-50M on this thesis. The question is whether Pedigree captures the category before consolidation happens.

---

## Slide 8: Traction - Design Partner

**Headline:** Wesco International (Fortune 500) validated every gap in our spec.

**The Wesco story:**
- Fortune 500 industrial distributor
- Head of IAM approached us with an articulated list of 8 governance gaps
- Currently blocking Copilot Studio deployment pending governance solution
- Active design partner - 90-day PoC in planning

**What success looks like:**
- Live graph with Wesco's Workday + Entra environment
- Automated cascade deprovision demo on simulated termination
- Complete audit bundle exportable for their compliance team
- PoC -> contract -> reference customer story

**Why this matters:** Wesco didn't come to us because of our marketing. They came because the problem is real and urgent. This is validated demand from a Fortune 500 security team.

---

## Slide 9: Business Model

**Headline:** Free Orphan List -> sticky governance platform -> $500K-$2M enterprise contracts

**The motion:**
1. Free: Orphan List (HRIS + Entra -> see your unowned agents in 48 hours)
2. Core: $75-100/agent/month
3. Enterprise: $150-200/agent/month

**Unit economics:**
- 1,000 agents x $100/mo = **$1.2M ARR/customer**
- 5,000 agents x $75/mo = **$4.5M ARR/customer**
- Enterprise contract range: **$500K-$2M ARR**

**The land-and-expand:**
- Land: CISO sees the Orphan List, approves paid rollout
- Expand: more agents onboarded, runtime gateway added, SoD policies authored
- Retain: lineage graph is load-bearing infrastructure - churn requires rebuilding years of history

---

## Slide 10: What's Built

**Headline:** Demo-ready MVP. 6-8 weeks to Wesco PoC.

**Already built:**
- FastAPI backend: humans, agents, policies, runtime evaluation, cascade, audit
- Mock Microsoft service (Dataverse + Graph) for realistic demo
- React UI backed by live API
- Neo4j + Postgres schemas
- Docker Compose demo stack
- Full documentation: PRD, architecture, API spec, threat model, 90-day roadmap
- CI/CD on GitHub Actions

**Critical gaps (known, addressable):**
- Real HRIS connectors (Workday/UKG)
- Real Entra connector (Graph API production)
- Persistent storage (schemas exist, not yet wired)
- Webhook auth (known security issue, documented)
- Multi-tenancy enforcement

**Timeline:** 6-8 weeks to Wesco PoC with focused engineering. 4-5 months to v1.0 production.

---

## Slide 11: 12-Month Plan

**Headline:** Wesco PoC -> $1.5M ARR -> seed/Series A raise

**Month 1-3:** Wesco PoC live. First enterprise customer proof.
**Month 4-6:** 2-3 additional design partners. Real HRIS connectors in production.
**Month 7-9:** $1.5M ARR. Raise seed/Series A on Wesco reference.
**Month 10-12:** 5 enterprise customers. Runtime MCP gateway in production.

**Success metrics:**
- 90%+ orphan attribution accuracy via ML
- <5ms p99 gateway latency
- 100% cascade deprovision success on HR events
- $1.5M+ ARR
- 2+ reference customers willing to speak publicly

---

## Slide 12: The Ask

**Headline:** [Funding amount TBD] to capture a $12B market with an unoccupied primitive.

**Use of funds:**
- Engineering: Close critical build gaps, stand up Wesco PoC, hire 2-3 engineers
- GTM: Enterprise sales hire, Microsoft partner certification
- Infrastructure: Production hardening, security audit, SOC 2 Type I

**Why the timing matters:** The graph moat compounds. Every customer, every year of lineage data, every app owner who adopts the console makes Pedigree harder to displace. First mover on the HRIS-native lineage primitive has a durable advantage.

**The bet:** Agent governance becomes a $5-10B standalone market won by whoever owns the authoritative human-agent lineage graph. That graph has to be HRIS-native, platform-agnostic, and hard to rip out. That's Pedigree.

---

*See also: [One-Pager](./one-pager.md) | [Executive Briefing](./executive-briefing.md) | [Full Investor Research](./investor-research.md)*
