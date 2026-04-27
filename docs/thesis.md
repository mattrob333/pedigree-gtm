# Pedigree - Thesis & Win Strategy

> **"We don't compete with the hyperscalers. We complete them."**

---

## The One-Sentence Thesis

Pedigree is the **platform-agnostic human-agent lineage layer** - the governance primitive that every enterprise needs regardless of whether they run Microsoft, AWS, Google, Salesforce, or custom AI agents.

---

## The Problem in Plain English

Enterprises are deploying thousands of AI agents right now. Copilot Studio bots. LangChain workflows. n8n automations. Zapier agents. Custom Python scripts. All of them need access to sensitive systems - HR data, financial records, customer databases, source code.

None of the existing tools answer the three questions that keep CISOs awake:

1. **Who is the named human responsible** when this agent takes a bad action?
2. **What is this agent allowed to access** - and did that scope silently expand when its creator got promoted?
3. **What happens to this agent when the human leaves the company?**

The answer today is: nobody knows. Agents accumulate. Credentials persist. Auditors are starting to ask.

---

## The Design Choice That Changes Everything

**Every enterprise has two org charts.**

The human one - in Workday, UKG, or ADP - is authoritative, auditable, and tied to HR events. When someone is hired, their access is provisioned. When they leave, it's deprovisioned.

The agent one does not exist. Agents live in `.env` files, scattered credentials, and untraceable service accounts. Nobody owns the cleanup.

**Pedigree treats agents as digital children of the humans who created them.**

- Every agent is a child node under a parent human in the live org graph
- Agents inherit a **strict subset** of the parent's current entitlements
- When HR fires the termination webhook, Pedigree walks the agent subtree and decommissions the entire tree in <60 seconds
- Every action is logged against the human-agent lineage - the audit trail auditors actually need

This single design decision solves all 8 governance gaps simultaneously.

---

## Why Platform-Agnostic is the Attack Vector

### The Mistake the Hyperscalers Are Making

Every hyperscaler is building governance for *their own* ecosystem:

- **Microsoft** Agent 365 governs Copilot Studio and Entra Agent ID workloads well. Non-Microsoft agents? Limited.
- **AWS** Agent Registry catalogs Bedrock AgentCore workloads. No HRIS. No human lineage.
- **Google** Cloud API Registry is tool-focused and developer-centric. Not enterprise IAM.

**The enterprise reality:** Large organizations don't run one cloud. They run Microsoft *and* Salesforce *and* AWS Bedrock *and* custom Python agents *and* n8n workflows. They need governance that spans all of it from a single source of truth.

### Our Position: The Layer Above the Stack

```
┌──────────────────────────────────────────────────────────┐
│                    PEDIGREE                               │
│      Platform-Agnostic Human-Agent Lineage Layer          │
│  Works with any agent, any cloud, any identity provider   │
└───────────────────────────────────────────────────────────┘
        ↕                   ↕                   ↕
  Microsoft Entra      AWS Bedrock         Salesforce
  Agent ID + 365       AgentCore           Einstein AI
  Copilot Studio       Lambda              Custom Agents
        ↕                   ↕                   ↕
┌──────────────────────────────────────────────────────────┐
│              HRIS (Workday / UKG / ADP)                   │
│         The Ground Truth for Human Identity               │
└──────────────────────────────────────────────────────────┘
```

Pedigree is the translation layer between the HRIS org chart (the one true source of human identity) and every agent platform. We don't replace Entra. We make Entra's governance complete.

---

## Why We Win Against Microsoft Specifically

This is the most important question. The honest answer:

**Microsoft is building a great identity layer. They are not building a governance layer.**

| Capability | Entra Agent ID + 365 | Pedigree |
|---|---|---|
| Agent identity | ✅ Best in class | Uses Entra as foundation |
| Multi-platform agents | ❌ M365/Copilot only | ✅ All agents, all clouds |
| HRIS-verified human parent | ❌ Owner field only | ✅ Core feature |
| Org chart lineage graph | ❌ | ✅ Core feature |
| HR-driven cascade deprovision | ❌ Manual | ✅ Automated <60s |
| Strict parent-scope inheritance | ❌ | ✅ OAuth 2.1 Token Exchange |
| SoD enforcement | ❌ | ✅ Policy engine |
| App owner console | ❌ | ✅ Core feature |

**The positioning:** *"Entra tells you who the agent is. Pedigree tells you why it exists, what it can do forever, and what happens when the human leaves."*

The partnership play - not the war: Microsoft Partner Network is how we enter enterprise accounts. "Pedigree-certified for Entra Agent ID" is a credible GTM motion that doesn't require fighting a $3T company.

---

## The Moat

The moat is **not** the credential broker, the DLP rules, or the runtime gateway. Those exist in pieces across 10+ vendors.

**The moat is the authoritative human-to-agent lineage graph wired to HRIS.**

Once a customer connects their Workday instance and every agent has a parent-human edge, ripping Pedigree out means:
- Rebuilding years of lineage history manually
- Re-certifying thousands of agents
- Rebuilding the audit trail from scratch

The platform becomes the **system of record for agent ownership**. Every other tool (Entra, gateways, IGA platforms) becomes a consumer via API.

This is the Workday play for HR, the Okta play for identity, the Snowflake play for data - applied to the fastest-growing identity category in history.

---

## The Investor Parallels

**The Okta parallel:** Okta didn't compete with Active Directory - it made AD usable across cloud apps. It became the identity layer every SaaS app integrated with. $17B market cap.

**The Snowflake parallel:** Snowflake didn't compete with data warehouses - it became the cross-cloud data layer. $50B+ market cap at peak.

**Pedigree's parallel:** We become the cross-platform governance layer that every enterprise needs regardless of which agent platforms they run. The HRIS org chart is already universal - we make it the universal governance primitive for AI agents.

---

*See also: [Competitive Analysis](./competitive.md) | [Market Research](./market-research.md) | [Why Now](./why-now.md)*
