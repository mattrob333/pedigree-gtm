# Wesco PoC Playbook

*90-day design partner plan for Wesco International / Anixter*

---

## Design Partner Context

**Company:** Wesco International (NYSE: WCC) - Fortune 500 electrical and industrial distribution company. $22B+ annual revenue. 50,000+ employees globally.

**Contact:** Head of IAM - has articulated the exact 8-gap governance spec that Pedigree addresses.

**Status:** Active design partner conversation. Blocking Copilot Studio deployment pending governance solution.

**Opportunity:** First enterprise customer. Reference story. Category proof. Seed/Series A enabler.

---

## Why Wesco is the Perfect Design Partner

1. **Fortune 500 credibility** - "Wesco International deployed Pedigree" is a reference that opens every subsequent enterprise conversation
2. **Articulated spec** - They came to us with the exact 8 gaps. We're not selling to them; we're solving a problem they already defined
3. **Urgent blocker** - Copilot Studio deployment is blocked. There is organizational pressure to resolve this, which means budget and timeline urgency
4. **Workday + Entra** - Standard HRIS + IdP stack that covers most F500 enterprises. Building for Wesco means building for the next 50 customers

---

## 90-Day PoC Plan

### Sprint 1: Discovery & Orphan List (Days 1-30)

**Objective:** Generate Wesco's Orphan List. Make the problem visible to the CISO.

**Work:**
- Connect to Wesco's Workday instance (read-only) via REST API
- Pull Entra Agent ID inventory (all registered agents in their tenant)
- Run attribution - match agents to humans via AadUserId, UPN, email
- Generate the Orphan List: agents with no resolvable human parent
- Deliver the Orphan List to the CISO team with risk scoring

**Success metric:** Generate a credible Orphan List within 48 hours of HRIS connection. CISO acknowledges the problem is larger than expected.

**Deliverable:** Orphan List report + live demo of the attribution UI

---

### Sprint 2: Parent Assignment & Scope Enforcement (Days 31-60)

**Objective:** Assign parents to the top 50 agents. Demonstrate scope enforcement.

**Work:**
- Guided parent assignment workflow for unattributed agents
- Scope envelope calculation for top 50 agents vs their parent's Entra entitlements
- Flag any agents where current access exceeds parent's scope (scope violations)
- Basic App Owner Console: show one target system (ServiceNow) its agent inventory

**Success metric:** 50 agents with confirmed parent assignments. At least one scope violation identified and documented. ServiceNow owner can see their agent inventory.

**Deliverable:** Scope violation report + App Owner Console demo

---

### Sprint 3: Cascade Demo & Contract (Days 61-90)

**Objective:** Live cascade deprovision demo. Generate audit bundle. Begin contract conversation.

**Work:**
- Set up synthetic test environment mirroring Wesco's production structure
- Simulate HR termination event (test user) in Workday
- Demonstrate full agent subtree cascade: all agents assigned to terminated user set to archived/deprovisioned
- Generate audit bundle: agent lineage, entitlements at time of deprovision, cascade timeline, compliance export
- Deliver SOX-ready audit artifact to Wesco compliance team

**Success metric:** Cascade completes in <60 seconds from Workday termination event. Audit bundle generated and reviewed by Wesco compliance team.

**Deliverable:** Live cascade demo + audit bundle + contract discussion

---

## Success Metrics (Full PoC)

| Metric | Target |
|---|---|
| Time to Orphan List | <48 hours from HRIS connection |
| Orphan attribution accuracy | >80% of agents resolved to a human |
| Scope violations identified | At least 5 flagged in real environment |
| Cascade deprovision time | <60 seconds from HR event |
| Audit bundle completeness | Accepted by Wesco compliance team |
| Contract conversation | Initiated by Day 75 |

---

## Reference Story Outline

After PoC success, Wesco becomes our first public reference. The story arc:

**Before Pedigree:**
- Head of IAM had no comprehensive list of AI agents in the environment
- Copilot Studio deployment blocked by security team
- No answer to "what happens to an agent when its creator leaves?"
- Audit team asking questions that couldn't be answered

**The PoC:**
- Orphan List generated in 48 hours - revealed X agents with no human owner
- Y scope violations identified (agents exceeding creator's access)
- Live cascade demo: Z agents decommissioned in 47 seconds on simulated termination

**After Pedigree:**
- Security team approved Copilot Studio deployment
- CISO can answer every agent governance question from the dashboard
- Compliance team has the audit bundle they need for SOX review
- Wesco is the model for how Fortune 500 enterprises govern their AI workforce

---

## NDA / Commercial Templates Needed

- Non-disclosure agreement (mutual)
- Design partner agreement (IP assignment, reference rights, pricing)
- Data processing addendum (HRIS data is sensitive)
- Professional services agreement (PoC delivery)

---

*See also: [GTM Strategy](./gtm-strategy.md) | [Unit Economics](./unit-economics.md)*
