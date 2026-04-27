# Objection Handling Scripts

*For investor conversations, sales calls, and CISO meetings*

---

## Investor Objections

### "Microsoft will just build this natively."

**Script:** "Microsoft is building a great identity layer — and we use it as our foundation. But there are three things Microsoft can't easily build: First, a deep HRIS integration with Workday, UKG, and ADP. Microsoft doesn't own those systems, and enterprise HR teams don't let Microsoft own the source of truth for their org chart. Second, the multi-platform governance story. Enterprise security teams need governance that spans Copilot Studio, LangChain, Salesforce agents, and custom builds — Microsoft's incentive is to optimize for M365. Third, the app owner console. This is a workflow product, not an identity product — Microsoft's product motion doesn't go there. The Okta story is the right analogy: Okta didn't compete with Active Directory, it made it complete. We're doing the same with Entra."

---

### "ServiceNow just bought Veza for $1B — aren't you too late?"

**Script:** "The $1B acquisition is the best possible validation we could have for this market. And it actually opens a door: Veza customers are now ServiceNow customers by accident — uncertain about roadmap, dealing with integration complexity, asking themselves if they need a $150B platform or a focused solution. The 12–18 month post-acquisition window is when we move. More importantly, Veza didn't have what Pedigree has: HRIS-native lineage, cascade deprovision on HR events, strict parent-scope inheritance, and the app owner console. That gap is what Wesco came to us with. It's real."

---

### "This market is too competitive."

**Script:** "Ten vendors solving pieces of the problem is actually a good sign — it means enterprise buyers are actively spending in this space. But look at what nobody has: the HRIS-native lineage graph with cascade deprovision. That specific primitive — treating agents as digital children of HR-verified humans — is unoccupied. Competitors do discovery, runtime, identity. None of them do lineage. That's our opening."

---

### "The build looks expensive. What does 'MVP scaffold' mean practically?"

**Script:** "Honest answer: we have a complete, working demo system — real API, real UI, mock Microsoft connectors, Docker stack you can spin up in five minutes. What we don't have yet is production HRIS connectors and persistent storage. Those are well-understood engineering problems, not research problems. Six to eight weeks to Wesco PoC with focused engineering. Four to five months to v1.0 production. The foundation — the architecture, the API contract, the data model, the documentation — is solid. We're not starting from scratch, we're finishing the last mile."

---

### "Why will CISOs buy from a startup vs an established vendor?"

**Script:** "CISOs buy from startups when the incumbent doesn't have the answer — which is exactly this situation. Entra Agent ID doesn't have HRIS-native cascade deprovision. ServiceNow doesn't have the lineage graph. The established vendors have adjacent products, not this product. Also: Wesco's Fortune 500 Head of IAM came to us. That's not a sales call we made. The problem is real and urgent enough that large enterprises are actively looking for point solutions, not waiting for the platform to catch up."

---

## Customer / CISO Objections

### "Isn't this just what Entra Agent ID does?"

**Script:** "Entra gives every agent a managed identity and some ownership metadata — and that's great, we use it as our foundation. Pedigree does something different: we wire that identity to the *live human org chart* in Workday, with parent-child relationships, scope caps, management-chain approvals, and automatic deprovision on HR events. Entra tells you *who* the agent is. Pedigree tells you *why* it exists and *what happens when the human leaves*. These are different problems."

---

### "We already have Veza / Astrix / a discovery tool."

**Script:** "Discovery tells you what exists. Pedigree tells you who owns it *forever*, enforces what it *should* be able to do, and cleans it up when the human leaves. Most of our early conversations have been with teams that already have a discovery tool — and still couldn't pass their last audit because they had no lifecycle management and no accountability chain. The Orphan List is the thing they couldn't generate before. Let us show you yours."

---

### "What about agents that need to outlive their creator — compliance bots, shared workflows?"

**Script:** "We support 'immortal' and 'org-owned' agent nodes with explicit exception workflows. The default is human-parented; exceptions are visible and auditable with a different approval chain. Your compliance bots won't disappear. But they will have a formal exception record — which is exactly what your auditors want to see. 'We have a process for this' is dramatically better than 'we don't know.'"

---

### "Latency on every tool call will kill agent performance."

**Script:** "Our gateway uses aggressive policy compilation and caching — target <5ms p99 added latency. For heavy checks we go async with clear escalation paths. We're also partnering with leading MCP gateways (Kong, Solo) so you can use best-of-breed wire while Pedigree supplies the policy brain. The latency concern is valid for badly-designed gateway architectures — we've designed ours specifically to avoid it."

---

### "This seems expensive. $100/agent/month adds up."

**Script:** "For 1,000 agents at $100/agent/month that's $1.2M ARR — less than one breach, less than one failed SOX audit, less than one FTE dedicated to manual agent cleanup. Most customers see 5–10× ROI in the first year from: unblocked AI productivity (the CIO/CEO value), reduced audit findings (the CISO value), and FTE savings on manual cleanup (the operational value). The orphan agent that triggers a breach will cost orders of magnitude more than the annual contract."

---

### "We're not sure Workday integration will be reliable enough."

**Script:** "HRIS reliability is a first-class SLA in our architecture. We use multi-connector design with fallback polling when webhooks fail — so a Workday outage doesn't mean agents stop being governed. We also support synthetic testing for HR event flows and have documented SLAs for cascade deprovision timing. The HRIS reliability concern is real; we've built the architecture to address it."

---

### "Who on your team has done enterprise IAM before?"

**Script:** "[Team answer — fill in when team is confirmed]. What I can tell you is that Wesco's Head of IAM, who has done enterprise IAM for a Fortune 500 for over a decade, reviewed our spec and said we got the problem right. We also have [advisors/technical partners] who have shipped at this layer before. We're building with the right practitioners in the room."

---

*See also: [Competitive Analysis](./competitive.md) | [GTM Strategy](./gtm-strategy.md)*
