# How Pedigree Works — Technical Explainer

---

## The Core Concept: Every Agent is a Child Node

The fundamental design decision: **every AI agent must be a child node of a verified human in the live HRIS org chart.**

This is not metadata. It is a hard constraint enforced at creation, at runtime, and at offboarding.

```
Workday (HRIS)
    └── Sarah Chen — Finance Manager
            ├── [Human entitlements: SAP Finance, SharePoint, Workday read]
            └── 🤖 Invoice Processing Agent
                    ├── [Inherited scope: SAP Finance read, SharePoint read]
                    ├── [Cannot access: Workday, email, HR systems]
                    └── [Status: ACTIVE — will cascade when Sarah departs]
```

When Sarah is terminated in Workday:
1. Workday fires a termination webhook
2. Pedigree receives the event within seconds
3. Pedigree walks Sarah's entire agent subtree
4. All agents are deprovisioned (Dataverse `statecode=1`, Power Platform archived)
5. An immutable audit bundle is generated: lineage, entitlements, cascade timeline
6. The entire process completes in <60 seconds

---

## The 5-Layer Architecture

### Layer 1: Shadow Org Graph

**What it does:** Ingests the HRIS system (Workday, UKG, or ADP) and builds a live graph of human nodes with manager chains, entitlements, and employment status. Pulls Microsoft Dataverse/Entra agent inventories and resolves each agent to an HRIS human via Entra ID, UPN, and email.

**Key outputs:**
- Complete human-agent lineage graph (Neo4j)
- Agent attribution: which agents are "owned" by which humans
- Orphan List: agents that cannot be attributed to any active human
- Risk scores based on access vs scope alignment

**Connectors (MVP):** Workday REST API + webhook, Microsoft Entra Agent ID + Graph API
**Connectors (roadmap):** UKG, ADP, Okta, Ping, ServiceNow HR

**The invariant:** Every agent in the environment must either resolve to an active human parent OR be explicitly marked as an orphan/exception with documentation.

---

### Layer 2: Credential Clone Engine

**What it does:** When an agent is created, Pedigree snapshots the parent human's live entitlements (Entra groups + HRIS roles + SharePoint access via Graph) and generates a scoped OAuth 2.1 credential for the agent that represents a strict *subset* of the parent's access.

**The key rule:** The agent's scope envelope can only be *tightened*, never silently widened. If the parent's access decreases (reorg, role change), the agent's access is automatically adjusted downward.

**Technical implementation:**
- OAuth 2.1 Token Exchange (RFC 8693) — derivative credentials, not copies
- Scope derivation: intersection of parent's entitlements and the minimum required for the agent's stated purpose
- Approval workflow: human manager chain must approve scope at creation and on recertification

---

### Layer 3: MCP-Aware API Brokerage Gateway

**What it does:** Sits between every agent and every target system. Intercepts every tool call, verifies the calling agent's identity against the lineage graph, checks the action against the parent human's *current* entitlements, evaluates SoD rules, applies DLP, and passes/blocks/redacts/escalates.

**Protocol support (MVP):** `/runtime/evaluate` endpoint — synchronous check for tool calls
**Protocol support (v1.1):** Full MCP-aware gateway with transparent proxy mode

**Latency target:** <5ms p99 added latency (aggressive policy caching + compiled rules)

**Decision outcomes:**
- `ALLOW` — action is within scope, logged, forwarded
- `BLOCK` — action exceeds scope or violates SoD, logged, rejected with clear error
- `ESCALATE` — action requires manager approval, request queued, agent notified
- `REDACT` — action allowed but response data DLP-filtered before returning to agent

---

### Layer 4: App Owner Console

**What it does:** Provides a UI surface for every target system owner (ServiceNow, Oracle, SAP, Salesforce, GitHub, Snowflake) that shows exactly which agents are calling their system, who the parent human is, what actions have been taken in the last 30 days, and provides one-click revoke.

**Why this matters:** Turns app owners into internal champions instead of victims. They go from "there are mystery agents calling my system and I can't stop them" to "I have full visibility and one-click control." This creates a powerful internal stakeholder group that actively wants Pedigree to succeed.

**Console features:**
- Agent inventory per system: name, parent human, creation date, last active
- 30-day action history: what the agent did, what it accessed
- Risk indicators: scope violations, SoD flags, unusual activity
- One-click revoke: immediately suspends agent access to the system
- Bulk actions: audit all agents owned by employees in a specific department

---

### Layer 5: SoD & DLP Runtime Engines

**What it does:**

**SoD (Segregation of Duties) Engine:**
Watches for toxic action combinations based on the parent human's org position. If a Finance Analyst's agent has already performed a "create vendor" action in this session, the engine blocks a subsequent "approve payment to vendor" action — because that combination would be blocked for the human.

Rules are authored in Rego (OPA) by the enterprise's existing IGA team, using the org-chart position and role as the policy context. This means governance teams don't need to learn a new policy language.

**DLP (Data Loss Prevention) Engine:**
Classifies data flowing back to the agent and applies redaction rules. A "retrieve customer record" action might return PII — the DLP engine redacts fields that exceed the parent human's data classification authorization before the data reaches the agent.

---

## The Data Flow (End-to-End)

```
1. HRIS Event (Workday termination)
   → Pedigree ingestion service receives webhook
   → Updates human node status to TERMINATED in graph
   
2. Cascade Planning
   → Graph query: all agent nodes with parent = terminated human
   → For each agent: plan deprovision sequence
   
3. Cascade Execution
   → Microsoft Power Platform: archive each Copilot Studio bot
   → Entra: update agent identity to disabled
   → All target systems: revoke agent credentials
   
4. Audit Generation
   → Write immutable audit record: lineage snapshot, entitlements at time of deprovision, cascade timeline
   → Export to compliance bundle (SOX/HIPAA/GDPR format)
   
5. Notification
   → CISO dashboard: cascade complete, N agents deprovisioned
   → App Owner Console: agents removed from each system's inventory
   → Orphan detection: any agents that couldn't be deprovisioned flagged for manual review
```

---

## Why This Architecture Wins

**The graph is the foundation.** Every other feature is a consequence of the lineage graph existing. Once the graph is built:
- Cascade deprovision is a graph traversal
- Scope enforcement is a graph query against parent's entitlements
- SoD is a graph query against the parent's org position
- The audit trail is the graph's state over time

**HRIS is the root.** The HRIS is the only system that every other identity system is downstream of. By rooting the agent graph in HRIS, Pedigree inherits the authoritative truth about human identity — not a copy, not a sync, the source.

**Platform-agnostic by design.** The graph model works regardless of whether the agents are Copilot Studio bots, LangChain chains, n8n workflows, or custom Python scripts. Any agent that can be registered and attributed to an Entra ID can participate in the graph.

---

*See also: [Architecture Document](./architecture.md) | [Product Requirements](./prd.md) | [Competitive Analysis](./competitive.md)*
