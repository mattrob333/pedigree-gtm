# Executive Briefing — Pedigree

*2-page summary for CIO/CEO and non-technical investor conversations*

---

## The Problem in Business Terms

Your company is deploying AI agents — software that acts autonomously on behalf of employees to automate tasks, retrieve data, and make decisions. This is good. It increases productivity.

But these agents create a governance problem that your existing systems were never designed to handle.

When Sarah from the finance team builds an AI agent to automate vendor approvals, that agent has access to your financial systems. When Sarah gets promoted, her access expands — and so does the agent's, silently. When Sarah leaves the company, her accounts are deprovisioned. The agent keeps running. With live credentials. Accessing financial systems. With no human owner.

Nobody knows this is happening. Your security team doesn't have a list of these agents. Your auditors are starting to ask.

This is not a hypothetical. It is happening at every major enterprise deploying AI today. The question is not *whether* you have orphaned agents — it's *how many.*

---

## The Pedigree Solution

Pedigree is a governance platform that ties every AI agent to the human who created it — using your company's existing HR system (Workday, UKG, or ADP) as the source of truth.

Think of it as the **org chart for your AI workforce**.

When an employee creates an AI agent:
- The agent is registered as a "digital child" of that employee in the org chart
- The agent's access is automatically limited to a subset of what the employee can access — it can never have more permission than its human parent
- The agent is approved by the managers and system owners it will interact with

When that employee leaves the company:
- HR updates Workday — this fires a termination event
- Pedigree automatically decommissions every agent owned by that employee within 60 seconds
- A complete audit record is generated, exportable for your compliance team

**The result:** No orphaned agents. No scope violations. A complete audit trail. Compliance teams can answer regulator questions. Security teams can approve AI deployments instead of blocking them.

---

## Why This Matters for Your Business

### Unblocking AI Productivity

Most enterprises that want to deploy Copilot Studio or AI automation tools are being slowed down — not by the technology, but by security and compliance teams who can't answer governance questions.

Pedigree answers those questions. With Pedigree deployed, your security team has the controls they need to approve AI deployments. Business units stop waiting. Productivity gains start.

### Compliance Readiness

SOX, HIPAA, and emerging AI regulations require organizations to demonstrate governance over systems that access sensitive data. AI agents access sensitive data by definition.

Pedigree generates the audit bundle your compliance team needs — automatically, in real time, in a format designed for regulator export.

### Protecting Against the Breach That Comes from Oversight

The most likely near-term AI security incident at a major enterprise will come from an orphaned agent — one that kept running after its human creator left, with access it should no longer have.

Pedigree eliminates this class of risk entirely.

---

## Why We Win (Business Version)

**We are not competing with Microsoft or Salesforce.** Pedigree works *on top of* whatever AI platforms you're already using — Microsoft Copilot Studio, AWS Bedrock, Google Cloud, Salesforce Einstein, custom tools. We don't require you to switch platforms.

**The comparison that matters:** Okta didn't replace Active Directory — it made it work across every cloud app. Pedigree doesn't replace Entra Agent ID — it makes agent governance work across every platform you run.

Once Pedigree is deployed and your HR system is connected, it becomes the system of record for AI agent ownership across your entire organization. Ripping it out is not a realistic option — it would mean manually rebuilding years of lineage history and re-certifying thousands of agents. This is the strategic moat that makes Pedigree a durable investment.

---

## The Market Opportunity

- **91%** of enterprises are already using AI agents
- Only **10%** have a governance strategy
- The non-human identity market is valued at **$12.2 billion in 2026**, growing to **$38.8 billion by 2036**
- ServiceNow paid **$1 billion** for Veza (December 2025) to enter this category — validating the market to investors and enterprise buyers

---

## Current Status and Next Steps

Pedigree has a working MVP demo with a live API backend, React UI, and mock Microsoft connectors. Our first design partner is Wesco International (a Fortune 500 distributor), whose Head of IAM has articulated the exact governance requirements Pedigree addresses — and is currently blocking Copilot Studio deployment pending a governance solution.

Our 90-day plan: live proof-of-concept at Wesco, demonstrating automated cascade deprovision on a simulated HR termination event. This produces the reference story and the technical validation we need to accelerate enterprise sales.

---

*Confidential — For executive and investor use only*
*Full technical documentation: github.com/mattrob333/pedigree-gtm*
