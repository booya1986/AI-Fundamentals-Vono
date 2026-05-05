# Vono Skills

Three Claude Skills built specifically for Vono's consulting practice. Each skill encodes a piece of Vono's methodology so any consultant — junior or senior — can produce work in a consistent Vono way.

## What's a Skill?

A Claude Skill is a folder with a `SKILL.md` file (and optional reference files) that Claude consults automatically when the right context arises. The skill description tells Claude *when* to use it; the body tells Claude *how* to use it.

Skills work in **Claude Code** (`~/.claude/skills/`), in the **Anthropic API** (via the Skills API), and in the **Claude apps** when shared with you.

## The three skills

### 1. [`rfp-writer/`](./rfp-writer/)
Drafts Hebrew-language RFPs for Israeli public-sector clients. Encodes section structure, mandatory clauses (חשכ"ל / משרד הרכש), Vono's tone of voice, and evaluation-criteria patterns.

**Triggers**: "תעזור לי לכתוב RFP", "צריך לנסח מכרז", "תכין מסמך דרישות"

### 2. [`rfp-response-analyzer/`](./rfp-response-analyzer/)
Analyzes vendor responses to an RFP — threshold-condition verification, scoring per the published criteria, comparison matrices, and red/yellow/green risk flagging. The natural pairing for `rfp-writer`.

**Triggers**: "תעבור על ההצעות", "תשווה בין הספקים", "תבדוק עמידה בתנאי סף", "תנקד את ההצעות"

### 3. [`vono-methodology/`](./vono-methodology/)
Codifies Vono's signature consulting methodology — project lifecycle (Discovery → Design → Build → Deploy → Stabilize), the one-pager, kickoff format, deliverable templates, RAG status rules, meeting summaries, and lessons-learned format. The on-ramp for new consultants and consistency-multiplier for senior ones.

**Triggers**: "תכין לי תוכנית עבודה ל-[לקוח]", "תנסח SOW", "תכין סדר יום לקיק-אוף", "תכתוב סיכום פגישה"

## Installation

### For Claude Code users on the Vono team

```bash
# Clone or copy this skills/ folder to your local Claude Code skills directory:
cp -r skills/* ~/.claude/skills/

# Verify they're loaded:
ls ~/.claude/skills/ | grep -E '(rfp-|vono-)'
```

Restart Claude Code. The three skills should now activate automatically when relevant.

### For shared use via the API

The skills can be loaded via the Anthropic API's Skills feature. See https://docs.anthropic.com/skills for the current API reference.

### For Claude.ai / Claude apps

Currently, sharing skills in Claude.ai is per-account. Each consultant should:
1. Clone this repo locally
2. Upload each skill folder as a `.skill` package (use `python -m scripts.package_skill skills/rfp-writer/` from the skill-creator)

## Customization

These skills are starting points. Vono should evolve them over time:

- **Add real RFPs** to `rfp-writer/references/` as examples
- **Add real vendor responses** (anonymized) to `rfp-response-analyzer/references/` for analysis examples
- **Update house style** in `vono-methodology/references/house-style.md` as it evolves
- **Add new deliverable templates** to `vono-methodology/references/deliverable-types.md`

Pull requests welcome from any team member.

## Maintenance

- **Owner**: [TBD — assign a senior consultant]
- **Review cadence**: Quarterly. Walk through each skill, check if rules still hold, update.
- **New skills**: When a recurring pattern emerges across 3+ engagements, create a skill for it.

## Why skills?

Consulting is high-stakes, high-variance work. The senior consultants are great. The junior ones are still finding their voice. Without a shared methodology, every engagement re-invents the wheel — sometimes well, sometimes not.

Skills are the bridge. They let any consultant, on any day, produce work that looks, sounds, and proceeds in a recognizable Vono way. The client buys a methodology, not just a person. These skills ensure the methodology shows up.
