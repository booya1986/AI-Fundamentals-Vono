# Lessons-Learned Format

Captured at the end of every phase, not just the end of the project. Why? Because by the time the project ends, you've forgotten half of what happened in Discovery.

## Template

```markdown
# Lessons Learned: [Phase Name] - [Project Name]
**Date**: YYYY-MM-DD
**Phase**: Discovery / Design / Build / Deploy / Stabilize
**Author**: [Vono team member who synthesizes]
**Reviewers**: [Vono team + relevant client members]

---

## What worked
[2-5 things that worked well. Be specific.]

1. **[Thing that worked]**
   - **Context**: When/where it happened
   - **Why it worked**: The mechanism
   - **Repeatable?**: Yes / Conditionally / No
   - **Recommendation**: Use again in [type of project / situation]

---

## What didn't work
[2-5 things that didn't. Be honest.]

1. **[Thing that didn't work]**
   - **Context**: When/where it happened
   - **Why it didn't**: Root cause analysis
   - **Impact**: What it cost (time, money, trust)
   - **What to change**: Specific recommendation for next time

---

## What surprised us
[Things we didn't expect, good or bad]

1. **[Surprise]**
   - **Expected**: What we thought would happen
   - **Actual**: What actually happened
   - **Lesson**: What this taught us about clients / situations like this

---

## Recommendations for the next phase

1. **[Specific recommendation]** - [Why, who acts on it, when]

---

## Recommendations for future Vono projects

1. **[Specific recommendation]** - [Type of project where it applies]
2. **[Specific recommendation]** - [Type of project where it applies]
```

## Field guidance

### "What worked"

Be specific. Not "communication was good". 

Bad:
> "Communication with the client was effective."

Good:
> **Tuesday morning status reports got read.**
> - **Context**: We sent status updates Tuesday at 9am instead of Friday at 5pm.
> - **Why it worked**: Senior sponsor was at desk on Tuesday. By Friday, he'd entered weekend mode.
> - **Repeatable?**: Yes - default to Tuesday for all banking clients.
> - **Recommendation**: Make Tuesday morning status the default. Adjust only if client specifically requests otherwise.

### "What didn't work"

Don't blame people. Identify the system or process gap.

Bad:
> "Vendor X was unhelpful."

Good:
> **Vendor X technical specification was 3 weeks late.**
> - **Context**: We expected the spec by week 2 of Build phase. Got it in week 5.
> - **Why it didn't work**: We didn't include penalty clauses for late deliverables in the contract. Vendor prioritized other work.
> - **Impact**: 3 weeks of Vono team idling, ~150K NIS in opportunity cost.
> - **What to change**: Add penalty clauses (5% of contract value per week of delay) to all vendor contracts going forward. Default in our SOW template.

### "What surprised us"

Surprises are gold. They tell us where our model of the world was wrong.

Good:
> **Senior bankers preferred phone calls over Slack.**
> - **Expected**: Like our tech clients, senior bankers would prefer async chat.
> - **Actual**: They didn't read Slack. They wanted phone calls and clear emails.
> - **Lesson**: For banking clients (and probably similar legacy industries), default to phone + email. Slack only for Vono-internal team coordination.

### "Recommendations for the next phase"

Concrete, actionable. With names if possible.

> **Reorganize the design doc by stakeholder, not by feature.**
> Why: When we showed by feature, sponsors got lost. When we organized by who-does-what, the sponsor immediately saw the impact on his team and engaged.
> Action: Tomer to reorganize before Tuesday's review.

### "Recommendations for future Vono projects"

This is the institutional knowledge. Be specific about the type of project.

> **In banking integrations, always plan for 2 weeks of architecture review with infosec before any code is written.**
> Why: We discovered late that infosec needed to approve the integration pattern. Cost us 10 days of rework.
> Applies to: All banking projects involving integration with core banking systems.

## Process

### When

- At every phase gate, run a 30-min lessons-learned review
- At project end, synthesize all phase lessons into a final memo
- Senior consultants meet quarterly to review accumulated lessons across all projects

### Who

- The Vono team that worked on the phase synthesizes the lessons
- The client business owner (if available) participates in the review
- Senior consultants review and decide what becomes institutional knowledge

### Output

- Per-phase lessons doc lives in the project's "one pane of glass" folder
- Final project lessons doc goes into the Vono knowledge base (skill: this one, or a linked Vono GPT / Notion / Confluence)
- Generic lessons (not client-specific) propagate to:
  - SOW template (e.g., add penalty clauses)
  - Engagement methodology (this skill)
  - Onboarding materials

## Common mistakes

### Lessons that aren't lessons
"Communication is important." That's not a lesson, that's a platitude. Lessons are specific.

### Lessons without action
"We learned that vendors miss deadlines." OK, what changes? If nothing changes, it's not a lesson — it's a vent.

### Saving lessons for the end
By the time the project ends, you've forgotten 70% of what happened in Discovery. Capture every phase.

### Not sharing lessons
A lesson learned by one team and not shared is a lesson lost. The whole point of this skill is consistency across all consultants.

### Hiding negative lessons
"We don't want this to embarrass us." Negative lessons are the most valuable. Document them. Anonymize if necessary, but capture.

## Cycle

```
Phase ends → Capture phase lessons → Apply to next phase
                ↓
        Project ends → Synthesize final lessons → 
                              ↓
                Update Vono templates / skills / training
                              ↓
                Next project starts smarter
```

This cycle is how Vono compounds. Without it, every project repeats the same mistakes.
