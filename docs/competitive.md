# Competitive Analysis

## The Landscape at a Glance

The agent governance space is crowded but fragmented. No competitor owns the HRIS-native lineage primitive. Everyone is approaching the problem from a different angle — none of them cover the full stack.

---

## The Full Comparison Matrix

| Capability | Pedigree | Microsoft Entra+365 | ServiceNow+Veza | Britive | PlainID | AWS Agent Registry | Astrix |
|---|---|---|---|---|---|---|---|
| Agent identity | Uses Entra | ✅ Best | ✅ Good | ✅ | ✅ | ✅ | ✅ |
| Multi-platform (non-MSFT) | ✅ All agents | ❌ Limited | ✅ Broad | ✅ | ✅ | ✅ AWS-focused | ✅ |
| HRIS-verified human parent | ✅ Core | ❌ Owner field only | ❌ Flat mapping | ❌ | ❌ | ❌ | ❌ |
| Org chart lineage graph | ✅ Core | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| HR cascade deprovision | ✅ <60s automated | ❌ Manual | ❌ | ❌ | ❌ | ❌ | ❌ |
| Strict parent-scope inheritance | ✅ Token Exchange | ❌ | ❌ | ✅ JIT/ZSP | ✅ | ❌ | ❌ |
| Runtime enforcement | ✅ MCP gateway | Partial | Via Veza | ✅ | ✅ | ❌ | ✅ |
| SoD in org terms | ✅ | ❌ | Partial | Partial | ✅ | ❌ | ❌ |
| App owner console | ✅ Core | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Audit bundle (SOX/HIPAA) | ✅ | Partial | Partial | ❌ | ❌ | ❌ | ❌ |

---

## Competitor Deep Dives

### Microsoft Entra Agent ID + Agent 365

**What they do:**
- First-class managed identities for AI agents
- Inventory and discovery for M365/Copilot Studio agents
- Conditional Access policies for agent workloads
- Agent 365 (GA May 2026): unified control plane, $15/user/month

**Their strengths:**
- Native integration with M365, Copilot Studio, Azure
- Massive enterprise distribution (already in procurement)
- Identity infrastructure is best in class

**Their gaps (Pedigree's opening):**
- Governance for non-Microsoft agents is limited
- No Workday/UKG HRIS connector — HR lifecycle is manual
- No org-chart parent-child lineage graph
- No cascade deprovision tied to HR termination
- No app owner console
- No SoD engine in org-chart terms

**The positioning:** *"Entra tells you who the agent is. Pedigree tells you why it exists and what happens when the human leaves."*

**The partnership play:** Position as "governance brain on top of Entra" — not competitor. Microsoft Partner certification is the enterprise GTM path.

---

### ServiceNow + Veza (acquired Dec 2025, $1B)

**What they do:**
- Veza: access graph, NHI discovery, human-to-agent mapping, blast radius visualization
- Now integrated into ServiceNow's identity security suite
- Broad enterprise distribution via ServiceNow's installed base

**Their strengths:**
- Best-in-class access graph and discovery
- Enterprise relationships via ServiceNow
- Human mapping capabilities

**Their gaps:**
- No strict parent-scope inheritance
- No HR-driven cascade lifecycle
- No app owner console as a product
- Acquisition creates roadmap uncertainty — Veza customers are reconsidering
- ServiceNow integration may dilute the focused agent governance story

**The positioning:** *"Veza tells you what exists. Pedigree tells you who owns it forever, enforces what it should be able to do, and cleans it up when the human leaves."*

**The opportunity:** Veza customers in transition are the most accessible early pipeline.

---

### Britive

**What they do:**
- Just-in-time (JIT) and zero standing privilege (ZSP) for cloud infrastructure and SaaS
- Runtime access enforcement
- Agent support added in 2025-2026

**Their strengths:**
- Strong runtime enforcement model
- Good multi-cloud coverage
- JIT/ZSP is a proven enterprise pattern

**Their gaps:**
- No HRIS integration — human parent is not org-chart verified
- No lineage graph
- No long-term ownership story — focused on ephemeral access, not persistent governance
- No cascade deprovision tied to HR events

**The positioning:** *"Britive is great for runtime. But who owns the policy? When the policy owner leaves, who cleans up? Pedigree is the source of truth that feeds Britive."*

---

### PlainID

**What they do:**
- Policy-based access control (PBAC)
- Runtime MCP enforcement
- Integration with enterprise identity providers

**Their strengths:**
- Mature policy engine
- MCP-aware enforcement
- Good IGA team integrations (Rego/OPA)

**Their gaps:**
- No HRIS-native org chart
- No cascade deprovision
- No human lineage model — policies are role/attribute based, not human-parent based

**The positioning:** *"PlainID enforces the policy. Pedigree defines what the policy should be — based on who the human parent is and what their org position allows."*

---

### AWS Agent Registry

**What they do:**
- Discovery and catalog layer for Bedrock AgentCore workloads
- Cloud-agnostic registration (can register non-AWS agents as metadata)
- MCP and A2A descriptor support
- Part of Amazon Bedrock AgentCore (preview, April 2026)

**Their strengths:**
- Cloud-agnostic catalog concept
- Developer-friendly API
- AWS distribution

**Their gaps:**
- No human ownership — catalog only
- No HRIS integration
- No lifecycle automation
- No governance enforcement — it's a registry, not a control plane
- AWS-focused despite "cloud-agnostic" positioning

**The positioning:** *"AWS tells you what agents exist. Pedigree governs them — who owns them, what they can do, and what happens when the human leaves."*

---

### Astrix Security

**What they do:**
- AI agent discovery and security platform
- Agent policy enforcement
- Fortune Cyber 60 recognition (2026)
- Series B funded

**Their strengths:**
- Broad discovery capabilities
- Policy enforcement at scale
- Strong security positioning

**Their gaps:**
- No HRIS lineage — agent ownership is not HR-verified
- No cascade deprovision on HR events
- No org chart graph
- Discovery-first, not governance-first

---

## When Pedigree Wins

- Customer has **strong HRIS** (Workday/UKG) and cares about audit/compliance (SOX, HIPAA, PCI)
- They have **already tried discovery tools** and still have rogue/orphan agents
- **App owners** are complaining about lack of visibility into what agents call their systems
- They are **Microsoft-heavy** but need governance beyond what Entra currently offers
- They are **multi-cloud** and need a platform-agnostic layer above all their agent runtimes

## When Pedigree Loses (Be Honest)

- Customer only runs Copilot Studio in M365 — Agent 365 may be sufficient
- Budget is extremely constrained — free Veza (now ServiceNow) tier may win
- No Workday/UKG — HRIS connectors are MVP; other HRIS requires custom integration

---

*See also: [Thesis & Win Strategy](./thesis.md) | [Objection Handling](./objections.md)*
