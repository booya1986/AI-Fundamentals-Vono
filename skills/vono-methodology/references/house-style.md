# Vono House Style — Writing Guide

The way Vono writes is part of the brand. Clients buy a methodology, but they live with our prose. These are the rules.

## Core principles

### 1. Short over long
A 2-paragraph status update beats a 2-page one. The senior client opens the document on a phone, between meetings. Write for that moment.

If you find yourself writing more than 1 page, ask: "What's the one thing the reader needs to know?" Lead with that. Cut the rest.

### 2. Concrete over abstract
Numbers, names, dates beat adjectives.

- ❌ "התהליך השתפר משמעותית"
- ✓ "זמן עיבוד RFP ירד מ-21 יום ל-9 ימים בממוצע (3 פיילוטים, אוקטובר-נובמבר)"

### 3. Active over passive
- ❌ "הוחלט להמשיך לפאזה הבאה"
- ✓ "ועדת ההיגוי החליטה להמשיך לפאזה הבאה"

In Hebrew, passive sometimes feels formal. Resist. Active makes it clear who decided, who acts, who's responsible.

### 4. Verbs over abstract nouns
- ❌ "ביצוע ניתוח של הצעות הספקים"
- ✓ "ננתח את הצעות הספקים"

Hebrew loves nominalizing verbs. The result is mushy, slow text. Pull the verb out.

### 5. One topic per paragraph
Long Hebrew paragraphs get skimmed. Break.

A paragraph should answer one question. If it answers two, split.

### 6. Single accountable owner
Every action item has a name. Not "the team", not "both sides", not "we'll discuss".

- ❌ "נדאג להעביר את המסמכים"
- ✓ "ענת תעביר את המסמכים עד יום ראשון, 12.10"

## Formatting rules

### Em dashes — banned

The em dash (—) is forbidden in Vono documents. Use:
- A regular hyphen with spaces: " - "
- A comma where appropriate
- Two sentences

This is a brand consistency rule. It makes text flow more naturally in Hebrew RTL contexts.

### No emojis in client documents

Internal Slack — fine. Client meetings — fine. Client documents — no.

Exception: the RAG status emoji 🟢🟡🔴 is allowed in Vono status reports because it's a meaningful signal.

### Number all enumerations
If you list things in order, number them (1, 2, 3). Use bullet points only for non-ordered items.

When the reader needs to reference an item — "let's discuss item 3" — numbers make that easy.

### Tables for comparisons
Anything that's a comparison (vendors, options, before/after) belongs in a table. Prose for comparisons fails.

### Define every acronym on first use
- ✓ "מערכת ניהול הלמידה (LMS) של הארגון"
- After first use: "LMS"

Even acronyms the senior reader knows. Write for the reader who doesn't.

### Quote, don't paraphrase
When referencing what someone said in a meeting, quote them directly. The quote is data; the paraphrase is your interpretation.

```markdown
מנכ"ל הבנק אמר בפגישת ה-15.10:
> "אנחנו לא נשקיע בפלטפורמה שלא נשלוט בה לאורך 5 שנים."

השלכה: יש לבחון מודלים של on-prem או escrow לקוד מקור.
```

## Document-specific rules

### Status reports
- Maximum 1 page (printed) or ~400 words.
- Open with RAG status: 🟢 / 🟡 / 🔴 + one sentence.
- Then: "What we did this week", "What's next", "Decisions needed", "Risks".
- Ship every Tuesday, not Friday. Friday status reports are read on Sunday at best.

### Steering decks
- Maximum 12 slides.
- Slide 1: status (RAG + 1-line summary).
- Slide 2: decisions needed today.
- Slides 3-N: context for each decision.
- Last slide: next milestone + when we meet next.

### Recommendation memos
- Maximum 2 pages.
- Open with the recommendation in 1 sentence.
- "Background", "Options considered", "Recommendation", "Risks", "Next step".
- Don't bury the recommendation — lead with it.

### Meeting summaries
Within 24 hours of any meeting. Format:
```markdown
פגישה: [שם הפגישה]
תאריך: YYYY-MM-DD
משתתפים: [רשימה]

## החלטות
1. [החלטה], אחראי: [שם]
2. [החלטה], אחראי: [שם]

## משימות פתוחות
1. [משימה], אחראי: [שם], דדליין: [תאריך]
2. [משימה], אחראי: [שם], דדליין: [תאריך]

## נושאים פתוחים
- [נושא לדיון בפגישה הבאה]

## ציטוטים מרכזיים
> "ציטוט ישיר ממשתתף שיש לו השלכה על ההמשך."
```

If a meeting summary doesn't fit this format, the meeting wasn't productive enough. Push back.

## Tone calibration

### To senior executives
- Direct. Confident. No hedging.
- Lead with conclusions. Provide reasoning if asked.
- Their time is valuable. Don't waste it on context they have.

### To peers (mid-level managers)
- Collaborative. Inquisitive.
- Walk through reasoning explicitly.
- Invite challenge.

### To technical specialists
- Specific. Technical.
- Use the right vocabulary; don't dumb down.
- Get to specifics fast.

### To users / front-line staff
- Empathetic. Practical.
- Focus on "what changes for you" and "how we'll help".
- Avoid jargon.

## Common mistakes

### Mistake: starting with context
"Following our meeting on October 15, where we discussed the various options for vendor selection..."

Cut. Start with the decision or recommendation. Context belongs in paragraph 2 or footnotes.

### Mistake: hedging language
"It might be possible to consider potentially exploring..."

Cut. "We recommend X." If you're not sure, say "We're 70% confident in X; here's what would shift it to 90%."

### Mistake: passive escape hatches
"The decision will be made..."

By whom? When? Tell us.

### Mistake: bullet-point soup
20 bullets in a row. Reader's eye glazes over.

Either group into 3-4 themes (with a sub-header per theme), or write a paragraph.

### Mistake: forgetting the reader
Write for the actual person who'll read it. Not for the file system. Not for posterity. Not to cover yourself.

If a senior client will read this on Saturday morning between coffee and yoga — make it readable on a phone, in 3 minutes.

## Final pass checklist

Before sending a Vono document:

- [ ] Em dashes removed
- [ ] No emojis (except RAG 🟢🟡🔴)
- [ ] Every action item has a single named owner
- [ ] Every claim has a date or a number
- [ ] Acronyms defined on first use
- [ ] Tables used for comparisons
- [ ] Lead with conclusion / recommendation
- [ ] Length appropriate to document type (status ≤ 1pg, steering ≤ 12 slides, recommendation ≤ 2pg)
- [ ] Read aloud — does it flow? Does Hebrew sound natural?
- [ ] If a senior person reads only the first paragraph, do they get the point?
