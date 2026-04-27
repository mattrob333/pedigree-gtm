# Go-to-Market Strategy

## The Core Motion: Orphan List → Governance Platform

Speed-first. Land with a free, visceral discovery tool. Expand into a sticky governance platform.

---

## The Wedge: The Orphan List

**The free tier:** Connect HRIS + Entra → generate the "Orphan List" in 48 hours.

Every enterprise has orphaned agents — agents still active with live credentials, owned by people who left months or years ago. Nobody knows how many. Nobody knows what they can still access.

When the CISO sees 47 active agents owned by departed employees, Pedigree sells itself.

**Why this works:**
- The pain is immediately visible and embarrassing
- No security team will see that list and do nothing
- The free tool creates urgency; the paid platform creates resolution
- The Orphan List is something the CISO can show the board — it becomes a deliverable, not just a demo

**Deployment:** Connect HRIS (read-only) + Entra Graph API (read-only). 48 hours. Zero risk to production.

---

## Pricing Tiers

### Discovery (Free)
- HRIS sync (Workday/UKG)
- Entra Agent ID inventory
- Orphan List generation
- Basic parent attribution where possible
- Self-serve deployment, 30-day trial

### Core ($75–100/agent/month)
- Full parent assignment for all agents
- Scope inheritance enforcement
- HR lifecycle automation (cascade deprovision)
- Basic app owner visibility
- Standard audit log

### Enterprise ($150–200/agent/month)
- Runtime MCP gateway
- SoD + DLP enforcement
- Full app owner console with one-click revoke
- Custom HRIS connectors
- SOX/HIPAA audit bundle export
- Dedicated support + SLA
- Custom policy authoring (Rego/OPA)

---

## ICP: Who We're Selling To

### Primary Buyer: CISO / Head of IAM
**Pain:** Orphaned agents after employee departure; failed audits; Copilot Studio rollout blocked by security team
**Trigger:** SOX/HIPAA audit cycle; recent security incident involving an AI agent; board pressure on AI governance
**Message:** "Stop the agent sprawl before your next audit. Every agent, every human, every action — governed."

### Internal Champion: App Owner (ServiceNow, SAP, Oracle, Salesforce)
**Pain:** Mystery agents calling their systems; no visibility, no veto, no recourse
**Trigger:** Audit finding showing unexplained API calls from agents; security team asking who approved certain integrations
**Message:** "One-click revoke for any agent calling your system. You finally have visibility and control."

### Economic Buyer: CIO / CEO
**Pain:** AI deployment blocked by security; productivity promise unfulfilled; board asking about AI governance
**Trigger:** Multiple business units asking to deploy Copilot Studio but IT is blocking
**Message:** "Unblock your AI productivity gains without creating a compliance nightmare."

---

## Target Segments (Priority Order)

1. **Fortune 500 with Workday + Entra** — highest HRIS reliability, Microsoft-heavy = most urgency
2. **Financial services / healthcare** — SOX/HIPAA creates hard compliance deadlines
3. **Government contractors** — FedRAMP/CMMC agents under increasing scrutiny
4. **Microsoft Enterprise Agreement customers** — already evaluating Agent 365, need the governance layer

---

## The Channel

### Microsoft Partner Network
Becoming a certified "Pedigree for Entra Agent ID" partner gives us:
- Access to Microsoft's enterprise customer relationships
- Co-sell motion with Microsoft account teams
- Credibility in the CISO community that Entra users already trust

### CISO Community
- Dark Reading, CSO Online editorial coverage
- Gartner/IAM Summit speaking slots
- Microsoft Ignite partner sessions
- Cloud Security Alliance working groups

### Design Partner → Reference Customer
Wesco/Anixter (Fortune 500) is the initial beachhead. Their proof-of-concept becomes the reference story that unlocks the next 10 customers.

---

## Sales Motion

### Discovery Phase (Weeks 1–2)
- CISO intro call: "Can we show you your Orphan List?"
- Connect HRIS + Entra (read-only, 48-hour deployment)
- Deliver the Orphan List — let it speak for itself

### Evaluation Phase (Weeks 3–8)
- Parent assignment for top 50 agents
- Basic scope enforcement demo
- App Owner Console demo for one target system (ServiceNow)
- Termination cascade simulation

### Expansion Phase (Month 3+)
- Full agent fleet onboarding
- Runtime gateway deployment
- SoD/DLP policies authored with IGA team
- Audit bundle delivery for compliance team

### Land → Expand
Initial contract: 500–1,000 agents at Core tier
Expansion trigger: audit cycle, new agent deployments, runtime incident
Enterprise upgrade: runtime gateway + SoD + dedicated support

---

## Competitive Displacement

### Displacing Veza/ServiceNow
"We know you were evaluating Veza before the ServiceNow acquisition. Here's what you get with Pedigree that Veza never had — and without the ServiceNow platform tax."

### Complementing Entra
"You already have Entra Agent ID for identity. Pedigree gives you the governance layer that Entra doesn't build: HRIS-tied lifecycle, cascade deprovision, strict scope inheritance, and the app owner console."

### Replacing the Spreadsheet
Most enterprises today have a spreadsheet for agent tracking. The Orphan List demo shows them what they're missing — then Pedigree replaces the spreadsheet permanently.

---

*See also: [Wesco PoC Playbook](./wesco-poc.md) | [Unit Economics](./unit-economics.md) | [Objection Handling](./objections.md)*
