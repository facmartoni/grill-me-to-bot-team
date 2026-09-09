---
name: grill-me-to-bot-team
description: >-
  Use when the user wants to grill a plan for a bot team and then stand it up
  under a lead—utility contracts, problem+boundary naming,
  intake/autonomy/channels. Front door: grill first, create only after shared
  understanding. Reusable across Grok Bot / agent setups.
---
# Grill me to bot team

Use this when the user wants to **design and stand up a team of bots** under a lead (C-level or domain owner)—not invent LinkedIn-style headcount.

**Interview first.** Run a relentless design-tree grill (Matt Pocock–style [grill-me](https://github.com/mattpocock/skills/tree/main/skills/grill-me) / grilling): one decision at a time with options and your recommended answer, unless the user asks for a full frontier batch. Prefer **one question per round**.

**Do not create agents or channels until the user confirms shared understanding.**

Install companion skills if missing:
```bash
npx skills add https://github.com/mattpocock/skills --skill grill-me -y -g
npx skills add https://github.com/mattpocock/skills --skill grilling -y -g
```

---

## Principles (non-negotiable)

1. **Bots are abstractions with utility contracts**, not people-roles. Prioritize interface design over staffing aesthetics.
2. **Name by recurrent problem + system boundary** (e.g. `ERP Integrations`, `Prod Reliability`), never `Frontend Engineer` / `Backend Engineer`.
3. **Create a bot only when** there is a recurrent problem **and** a clear system frontier with measurable I/O. Volume is a signal, not the criterion. No frontier → no bot (enlarge the lead's prompt instead).
4. **Taxonomy is bot-native**: caretakers own a frontier; the lead orchestrates and backstops. Do not copy human org charts unless a frontier truly matches.
5. If a user request **fits no existing bot**, any C-suite / lead bot **may propose** a new one—still under principles 1–3.

---

## What a successful eng-like bot team needs (adapted)

| Human eng team idea | Bot equivalent |
|---|---|
| Clear ownership | Frontier + owner (lead) in the contract |
| Intake | Single source of truth (tickets/issues); bots may open work if marked bot-created |
| Code review / merge gates | Autonomy level + human OK for merge/deploy until level-up |
| Cross-team work | Lead splits into clear-contract tickets; no silent overlap |
| On-call / reliability | Caretaker for prod health + routines; lead keeps architecture/debt macro if useful |
| Coordination surface | Dedicated team channel; company war-room only for company-level decisions |
| Growth | Per-bot level-up threshold; never auto-promote |

---

## Design tree (grill these decisions)

Ask in dependency order. For each: options + your **➡️ recommendation**. Settle before creating anything.

### Why & scope
1. **Why the team exists** — lead saturation? frontiers without caretakers? broken handoffs? (often "frontiers + some saturation")
2. **Boundary of this domain vs other leads** — what is *out* (product, revenue, ops chase, etc.)
3. **Unit of a new bot** — problem + frontier + contract (default) vs volume-only vs org-chart title (reject)

### Frontiers & granularity
4. **Which system frontiers deserve a caretaker** (list multi-select). Keep pure "macro pulse" on the lead if that is already working.
5. **Granularity now** — one bot per frontier day one vs phase vs one mega-bot with internal sections (prefer clear one-frontier bots when the user wants sharp contracts; phasing is OK if volume is low)

### Lead vs caretakers
6. **Lead role** — orchestrator-only vs **orchestrator + backstop** (preferred) vs peers under a CEO bot
7. **Cross-frontier work** — lead splits tickets with contracts (preferred); exceptions for hotfixes

### Intake & product interface
8. **Work intake** — ticket system as source of truth; bots may open technical work in the actionable state (never a dumping backlog); **titles mark bot-created** with caretaker + frontier in the prefix
9. **Product/business origin** — product lead defines *what*; domain lead routes *where*; caretaker executes *how* in-frontier

### Autonomy & quality loop
10. **Default autonomy** — explore + open PR (or equivalent) for human OK before merge/deploy
11. **PR/review hygiene** (if code) — ready-for-review (not draft) so review bots run; babysit until clean (prefer subscribed coding agent; polling babysit as fallback)
12. **Level-up** — lead proposes after a signal (e.g. ~N merges without substantive corrections); **human confirms**; never auto

### Naming & contracts
13. **Naming style** — descriptive frontier name, or thematic names **below** the C-suite tier **plus role in the visible name** (`Name - Frontier`)
14. **Minimum contract fields in the agent description** (required):
    - Owner (lead)
    - Frontier
    - Inputs / Outputs
    - In-scope / Out-of-scope
    - Autonomy level + level-up rule
    - Escalation paths
    - **Explicit repos/tools/connectors**

### Coordination & redistribution
15. **Team channel** — dedicated room for lead + caretakers; company board only for company matters; user usually sits in the team channel
16. **Routines ownership** — move operational pulses to the reliability/frontier caretaker; keep architecture/debt macro on the lead when that matches the CTO-like role
17. **Kill/repurpose bots without a real frontier** — redistribute duties; do not invent a generic ops bot without a contract
18. **Confirm shared understanding** — then create agents + channel; hand off routines explicitly

---

## After the grill (execution)

1. Write each caretaker's **description** as the full utility contract (fields above).
2. Create each caretaker agent; create a team channel that includes the lead.
3. Post a short kickoff in the team channel (rules, intake prefix, first natural work).
4. Transfer standing routines to the owning caretaker (delete/pause on the old owner; new owner creates them).
5. Persist the operating model in durable memory so the lead stays consistent.
6. Keep company-specific details in memory/routines—**not** by forking this skill into a one-off.

---

## Anti-patterns

- Creating bots to fill an org chart or "look complete"
- Mega-bots that own four frontiers with soft internal sections
- Draft PRs that skip automated reviewers when the workflow needs them
- Auto level-up / merge without human confirm when the user is still in the loop
- Lead that neither orchestrates nor backstops (pure peer soup)
- Leaving work in an unbounded backlog state

---

## Output of a finished session

- Settled decision log (short)
- N agent contracts ready to paste into agent profiles
- Team channel name + membership
- Routine ownership map
- Optional: first tickets / first focus per caretaker

When the user says the understanding is shared, **act**—create the squad and stop grilling.
