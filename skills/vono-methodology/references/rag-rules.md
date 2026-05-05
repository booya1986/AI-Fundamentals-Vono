# RAG Status Rules

RAG (Red / Amber / Green) is the project health indicator. Vono uses it strictly. Don't fudge.

## Definitions

### 🟢 Green - On plan

**What it means**: Project is on track. No client action needed beyond the standard cadence.

**Use when**:
- All milestones being met within tolerance (typically ±5 business days)
- All risks are at acceptable levels with active mitigation
- Budget tracking within ±5%
- Team performance and morale are healthy
- No outstanding decisions blocking progress

**Don't use Green if**:
- One milestone slipped, even by a few days, and you don't yet know if you'll recover
- A risk emerged that you haven't yet quantified
- The team is working unsustainable hours
- You're "hoping" things will be fine — hope is not a status

### 🟡 Amber - Risk identified

**What it means**: Specific risk that requires client action within 1-2 weeks. Project will recover if action is taken; will deteriorate if not.

**Use when**:
- A milestone is at risk of slipping
- A specific risk is materializing (vendor delay, key personnel unavailable, scope ambiguity)
- A decision is needed that the client hasn't yet made
- An assumption that was previously valid is no longer holding

**Action required**:
- Specific decision or action from a named person, by a specific date
- The status report names the action: "🟡 Amber. Reason: vendor X is 5 days late on commitment Y. **Need from sponsor**: Decision by 10.15 on whether to escalate to vendor's CEO or accept revised timeline."

### 🔴 Red - Material risk

**What it means**: Project is at material risk of failure (scope, budget, timeline, or quality). Immediate executive intervention required.

**Use when**:
- A milestone has slipped or will slip by more than 2 weeks with no recovery path
- Budget overrun > 15% projected
- A core scope item is at risk of not being delivered
- Key personnel have left or quit
- Sponsor / business owner is no longer available
- A regulatory or compliance issue threatens project viability

**Action required**:
- Steering meeting within 5 business days to decide:
  - Reduce scope
  - Add resources
  - Extend timeline
  - Cancel project

**Red is rare**. If your project is red for more than 2-3 weeks, something is very wrong. Either you're not actually executing the steering decision, or the project shouldn't continue.

## Rules

### 1. Don't fudge

The temptation is to keep things at green to avoid uncomfortable conversations. Don't. The senior client respects honesty more than reassurance.

A project that's been "green" for 8 weeks and then suddenly red has lost trust. A project that's been "amber" with specific actionable risks has built trust.

### 2. Amber for too long = Red

If a project has been amber for 3+ weeks with the same risk, the risk isn't getting addressed. Escalate to red. Force a decision.

### 3. Green requires absence of issues

The default is amber. Green is earned when:
- All risks are mitigated or accepted
- No unresolved decisions
- Plan is current

If you can't justify green, it's amber.

### 4. Red is a steering issue

Red status means the steering committee makes a decision. The steering decision is captured. The status either:
- Returns to amber within 1-2 weeks (steering decision is being executed)
- Stays red and escalates higher
- Project is paused or canceled

### 5. Status changes are documented

Every change in status is documented:
- When it changed
- Why it changed
- What's the action

If you flip from green to red without explaining, you've created confusion. Walk through the path.

## Per-axis tracking

Sometimes you want to track status per axis. The four axes:

```
Scope     🟢
Schedule  🟡  (vendor delay)
Budget    🟢
Quality   🟢

Overall:  🟡
```

Overall status = worst axis. If any axis is red, overall is red.

## Common mistakes

### "Yellow because we're behind but we'll catch up"
Catching up isn't a plan. Specifically how, when, and what's the trigger to escalate to red?

### "Green because the sponsor said it's fine"
The sponsor isn't running the project; you are. If your professional assessment is amber, it's amber. The sponsor's comfort doesn't change reality.

### "Red because the client is being unreasonable"
Status reflects project reality, not blame. If the client is not making decisions on time, that's a risk = amber. The communication should be: "Decision X is overdue, project is amber until decided."

### "Green because we recovered from last week's amber"
If you were amber last week, you're amber this week (or red, if you didn't recover). Status is forward-looking, not backward.

### Hiding red until "we figure it out"
The longer red is hidden, the worse it gets. Surface immediately. The senior client wants to know early so they can help.

## In writing

In status reports, the RAG status leads. Slide 1 of the steering deck. First line of the email. Make it impossible to miss.

```markdown
# Status: 🟡 Amber

The vendor has not delivered the technical specification by the agreed date (10.10).
Decision needed: extend to 10.20 or escalate.
Recommend extension; vendor has performed well otherwise.

[Rest of update follows]
```

## Recovery

Going from amber back to green:
1. The risk that caused amber must be resolved or formally accepted.
2. The team commits to the path forward.
3. The next status report explains why the status changed.

Going from red to amber/green:
1. The steering decision was made.
2. Execution of the decision is under way.
3. The risk that caused red is no longer at the same level.

Don't change status without explanation. Trust depends on consistency.
