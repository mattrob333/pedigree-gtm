# Pedigree - One-Pager

*Leave-behind for CISO meetings and investor conversations*

---

## 🏷️ Pedigree - Every Agent Has a Pedigree.

**The human org chart for AI agents.**

---

### The Problem

Enterprises are deploying thousands of AI agents across sensitive systems - Copilot Studio bots, LangChain workflows, Zapier automations, custom Python agents. None of their existing IAM tools answer the three questions that matter:

- **Who owns this agent?** Not a tenant or service principal - a *named human* accountable for its actions.
- **What is it allowed to access?** Did scope silently expand when its creator got promoted?
- **What happens when the human leaves?** Right now: nothing. The agent keeps running with live credentials.

The result: orphaned agents. Scope violations. Audit failures. Compliance exposure. And nobody knows how bad it is because nobody has the list.

---

### The Solution

Pedigree treats every AI agent as a **digital child of a verified human** in the live HRIS org chart.

- Agents **inherit a strict subset** of their parent's entitlements - they can never silently exceed the parent's access
- When HR fires the termination event in Workday, Pedigree **automatically decommissions the entire agent subtree** in under 60 seconds - with a complete audit bundle
- **Every action is logged** against the human-agent lineage for SOX, HIPAA, and regulator export
- A **one-click App Owner Console** gives ServiceNow, SAP, Oracle, and Salesforce owners full visibility and control over every agent calling their systems

---

### Why We Win: Platform-Agnostic

Most governance tools are built for one ecosystem. Enterprises run five.

Pedigree works across **Microsoft, AWS, Google, Salesforce, and custom agents** - platform-agnostic by design. We don't compete with Entra Agent ID. We make it complete.

> *"Entra tells you who the agent is. Pedigree tells you why it exists, what it can do forever, and what happens when the human leaves."*

**The moat:** Once the HRIS org chart is wired and the agent fleet is mapped, ripping Pedigree out means rebuilding years of lineage history manually. The platform becomes the system of record - every other tool consumes it via API.

---

### Market

| Metric | Number |
|---|---|
| NHI market 2026 | $12.2 billion |
| NHI market 2036 | $38.8 billion |
| Enterprises using AI agents | 91% |
| Enterprises with a governance strategy | 10% |
| ServiceNow acquires Veza (category validation) | $1 billion |

---

### Traction

**Design partner:** Wesco International / Anixter (Fortune 500). Head of IAM has articulated the exact 8-gap governance spec. Currently **blocking Copilot Studio deployment** until Pedigree exists. This is our 90-day PoC - success here is category proof.

---

### Business Model

- **Free:** Orphan List (connect HRIS + Entra -> see your unowned agents in 48 hours)
- **Core:** $75-100/agent/month - parent assignment, scope enforcement, lifecycle automation
- **Enterprise:** $150-200/agent/month - runtime MCP gateway, SoD/DLP, dedicated support

**Unit economics:** 1,000 agents x $100/month = **$1.2M ARR per customer.** Enterprise contracts: $500K-$2M ARR.

---

### What's Built

Working FastAPI backend, React UI, mock Microsoft connectors (Dataverse + Graph), Neo4j + Postgres schema, Docker demo stack, CI/CD. Full documentation suite (PRD, architecture, API spec, threat model, roadmap). Demo-ready MVP scaffold.

**Next:** Real HRIS connectors, persistent storage, runtime gateway. **Wesco PoC ready in 6-8 weeks of focused engineering.**

---

### Links

- **Product repo:** github.com/mattrob333/pedigree4
- **Investor hub:** mattrob333.github.io/pedigree-gtm
- **Category:** Human-Lineage Agent Governance
- **Stage:** Seed

---

*Confidential - For investor and partner use only*
