---
name: vono-methodology
description: Use this skill whenever a Vono consultant is structuring a new client engagement, drafting a project plan, preparing a kickoff, writing meeting summaries, defining deliverables, or running any phase of a consulting project. Trigger when the user mentions starting a new client, building an SOW, scoping a phase, planning a kickoff, structuring deliverables, writing status updates, or codifying lessons-learned. Trigger even if the user says things like "תכין לי תוכנית עבודה ל-[לקוח]", "תנסח SOW", "תכין סדר יום לקיק-אוף", "תכתוב סיכום פגישה", "איך אני בונה roadmap לפרויקט", or "צריך מתודולוגיה לעבודה מול הבנק". This skill encodes Vono's signature consulting methodology — the project lifecycle, kickoff format, phase gates, deliverable templates, communication patterns with clients, and the house tone of voice. It is the on-ramp for new consultants and the consistency-multiplier for senior ones.
---

# Vono Methodology Skill

This skill codifies how Vono runs consulting engagements. It exists to make every consultant — from first-week hire to 10-year veteran — produce work that looks, sounds, and proceeds in a recognizable Vono way.

## When to use

Use this skill when the user is:
- **Starting a new client engagement** and needs a project plan, SOW, or kickoff agenda
- **Inside an active project** and needs a phase-gate review, status update, or steering deck
- **Writing client-facing artifacts** — meeting summaries, decision logs, status reports, change requests
- **Scoping or estimating** a new piece of work
- **Onboarding a new team member** to a Vono engagement
- **Capturing lessons-learned** from a completed phase

Do NOT use this skill for:
- RFP-specific work (use `rfp-writer` and `rfp-response-analyzer`)
- Deeply technical implementation (use the right specialized skill)
- Pure marketing or sales materials (this is internal/client-facing methodology, not pitches)

## The Vono lifecycle

Every Vono engagement passes through **5 phases**, each with explicit entry/exit criteria. Don't skip phases. Don't blur them. Read [`references/lifecycle.md`](references/lifecycle.md) for the full definitions and gate conditions.

```
1. Discovery        →   2. Design        →   3. Build         →   4. Deploy        →   5. Stabilize
   (1-3 weeks)          (2-6 weeks)          (varies)             (1-4 weeks)          (1-3 months)
   What is the          What is the          Make it.             Roll it out          Monitor and
   real problem?        right answer?                             carefully.           hand over.
```

**Phase gates**: between each phase, run a 30-minute review with the client. The deliverable from the prior phase is reviewed; explicit approval to proceed is captured in writing. No verbal "yeah, looks good" — written approval, in the project log.

## The "Vono one-pager"

Every engagement starts with a one-page document. Even multi-million-shekel projects. Read [`references/one-pager-template.md`](references/one-pager-template.md).

The one-pager contains:
1. **Why** — what problem are we solving, why now
2. **What** — the deliverable, in one sentence
3. **Who** — single accountable owner on each side, named
4. **When** — phase milestones, not Gantt details
5. **What we need** — explicit dependencies on the client
6. **What we don't do** — out-of-scope items

The one-pager is the contract. The SOW formalizes it. If the SOW says something the one-pager doesn't, raise a flag.

## House tone of voice

Vono communicates in writing more than in meetings. Read [`references/house-style.md`](references/house-style.md) for the full guide. The summary:

- **Short over long**. A 2-paragraph status update beats a 2-page one. The senior client is busy.
- **Formal Hebrew** in client documents. Active voice. Verbs over abstract nouns. *"החלטנו על..."* not *"הוחלט בנוגע ל..."*.
- **Number every recommendation**. Vague suggestions don't survive contact with steering committees.
- **One topic per paragraph**. Long Hebrew paragraphs get skimmed.
- **No em dashes**. House rule. Use a regular hyphen with spaces or commas.
- **No emojis** in client documents. Internal team chat — fine.
- **Quote, don't paraphrase** when referencing what someone said. The quote is data; the paraphrase is your interpretation.

## Meeting cadence and formats

Read [`references/meeting-formats.md`](references/meeting-formats.md). Standard rhythm for a typical engagement:

- **Kickoff** (week 1) — ~90 minutes. Specific agenda. Decisions captured live.
- **Weekly checkpoint** with project sponsor — 30 minutes. RAG status (red/amber/green) + 1-3 decisions needed.
- **Bi-weekly steering** with executive — 30 minutes. Higher-altitude. Strategic risks.
- **Phase-gate review** — 30-60 minutes. Formal sign-off on the prior phase.

Every meeting needs a **summary in Vono format** within 24 hours. Read [`references/meeting-summary-format.md`](references/meeting-summary-format.md).

## Deliverable templates

Vono produces a small number of deliverable types. Don't invent new formats — use these. Read [`references/deliverable-types.md`](references/deliverable-types.md).

The core seven:
1. **One-pager** (engagement scope)
2. **SOW** (contractual)
3. **Status report** (weekly)
4. **Steering deck** (bi-weekly)
5. **Phase-gate document** (per phase)
6. **Recommendation memo** (when client decision is needed)
7. **Final report** (closing)

## RAG status — Vono's definition

Read [`references/rag-rules.md`](references/rag-rules.md).

- **🟢 Green** — On plan. No client action needed.
- **🟡 Amber** — Risk identified. Specific client action needed within 1-2 weeks.
- **🔴 Red** — Project is materially at risk. Immediate steering decision required.

Don't fudge. A project that's been "amber" for 4 weeks is actually red. A project where you're hiding bad news on green to keep the client calm is the worst kind of red.

## Workflow when invoked

When this skill activates, follow this decision tree:

### Case 1: User is starting a new engagement

1. Ask 5 questions if not yet known: client identity, problem statement, who's the sponsor, timeline pressure, budget envelope.
2. Generate a **one-pager** following the template.
3. If they want SOW also — generate it after the one-pager is approved.
4. Suggest a kickoff agenda based on the kickoff format.

### Case 2: User is mid-project

1. Identify which phase they're in.
2. Use the phase's specific deliverables and tools.
3. If they're stuck on RAG status, walk through the rules.
4. If they need a meeting summary or status report, use the templates.

### Case 3: User is writing a client document

1. Identify deliverable type (status / steering / recommendation / phase-gate / final).
2. Use the matching template.
3. Run a final pass against house-style rules.

### Case 4: User wants to capture lessons-learned

1. Walk through the standard lessons-learned format from [`references/lessons-learned.md`](references/lessons-learned.md).
2. Categorize: what worked, what didn't, what we'd do differently.
3. Be specific. "Communication was bad" is useless. "Status updates went out on Friday at 5pm and were ignored over weekend; moving to Tuesday morning" is useful.

## House rules across all situations

### Single accountable owner
Every deliverable, every decision, every action item — has exactly **one** named owner. "The team" is not an owner. "Both sides" is not an owner. Names are owners.

### No surprises
The client should never learn bad news in a steering meeting. By the time it's in steering, it should already be in the consultant's pre-call with the sponsor. If something will be on the next steering, the sponsor knows about it the day before.

### Decisions in writing within 24 hours
Verbal decisions don't exist. Either it's in a meeting summary, an email, or it didn't happen.

### One pane of glass
Every engagement has one place where the project status lives. Pick a tool (shared doc, Confluence page, project portal). All consultants and the client know where to look.

### Push back, with respect
If the client wants something we know will fail, our job is to push back — once, in writing, with reasoning. If they still want to proceed after we've made the case, we proceed. We don't litigate the same point three times.

## Why this matters

Consulting quality varies. The senior consultants are great; the new ones are still finding their voice. This skill is the bridge — it lets every engagement, regardless of who's running it, deliver in a recognizable Vono way. Clients who hire Vono are buying a methodology, not just a person. This skill ensures the methodology shows up.
