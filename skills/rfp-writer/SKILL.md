---
name: rfp-writer
description: Use this skill whenever a consultant needs to draft, review, or restructure a Hebrew-language Request for Proposal (RFP) for an Israeli public-sector client - government ministries (משרד החינוך, משרד הרכש, משרד הביטחון), the Treasury (חשכ"ל), municipalities, banks, healthcare networks, or any procurement that follows Israeli public-procurement standards. Trigger this skill when the user asks to write an RFP, draft a tender, build a מכרז, prepare procurement documents, or create a דרישות לספקים document. Trigger even if the user says "תעזור לי לכתוב RFP", "צריך לנסח מכרז", or "תכין מסמך דרישות". The skill encodes Vono's tone of voice, the canonical section structure, mandatory clauses for Israeli public procurement, and common evaluation-criteria patterns.
---

# RFP Writer (Vono / Israeli Public Sector)

This skill helps a Vono consultant write Hebrew RFPs that comply with Israeli public-procurement standards (תקנות חובת המכרזים, נהלי החשכ"ל, ת"י 27001, ת"ק 5568) and match Vono's house style.

## When to use

Use this skill when:
- A consultant needs to write an RFP for a public-sector client (banks, ministries, municipalities, government corporations).
- The user supplies a brief — even one sentence like "מכרז למערכת CRM למשרד החינוך, תקציב 3M ש״ח, 18 חודשים" — and expects a full first draft.
- The user wants to review or restructure an existing RFP draft against the canonical structure.
- The user wants help drafting a specific section (e.g., "תכתוב לי תנאי סף לפרויקט סייבר ארגוני").

Do NOT use this skill for:
- Private-sector commercial proposals where Israeli public-procurement rules don't apply (use plain commercial-proposal patterns).
- Vendor responses to RFPs (use `rfp-response-analyzer` instead).
- General-purpose Hebrew business writing.

## Workflow

Follow these steps in order:

### 1. Clarify scope

Before writing a single section, confirm with the user:

- **Client identity**: who is the procuring body (bank, ministry, municipality)? This drives compliance requirements.
- **Subject matter**: technology / service / construction / hybrid?
- **Budget envelope**: roughly known? affects threshold conditions and bid-bond size.
- **Timeline**: when must vendor responses arrive, when does work begin?
- **Critical constraints**: dedicated tenant required? on-prem only? Hebrew-only deliverables? specific certifications mandated?

If the user supplied this in the brief, summarize back and proceed. If not, ask focused questions — never invent constraints that the client may not actually want.

### 2. Pick the section template

Read [`references/section-templates.md`](references/section-templates.md) and select the template that matches the client and subject. Three variants exist:

- **Technology / system procurement** (CRM, LMS, BI, infrastructure)
- **Professional services** (consulting, training, implementation labor)
- **Hybrid** (system + ongoing services / SLA)

Don't mix sections from different templates without justification — each is calibrated to a different procurement category.

### 3. Draft the body

Write each section in order. For each section:

- **Use formal Hebrew (לשון רשמית)**. Active voice over passive. Verbs over abstract nouns. "המערכת תספק תמיכה" beats "המערכת תהווה מקור לתמיכה".
- **Be concrete**: numerical thresholds, named standards (`ת"י 27001`, `ת"ק 5568`), specific deliverables. Vague language ("מערכת איכותית") creates legal ambiguity and gets challenged.
- **Number everything**. Sections, sub-clauses, requirements. Vendors and reviewers need to reference clauses precisely.
- **One requirement per clause**. If a clause says "המערכת תתמוך ב-Hebrew ובאבטחת מידע" — split it. Reviewers will mark it as one requirement and miss half the intent.

### 4. Insert mandatory clauses

Read [`references/mandatory-clauses.md`](references/mandatory-clauses.md) and insert every clause flagged as **mandatory for the client type**. These are non-negotiable:

- Tax / corporate compliance certificates (אישור ניהול ספרים, עוסק מורשה)
- Israeli buy-local preference (העדפת תוצרת הארץ) when applicable
- Information security baseline (ת"י 27001) for any data-processing system
- Accessibility (ת"ק 5568) for anything user-facing
- Bid bond (ערבות מכרז) sized appropriately to project value
- No-conflict-of-interest declaration
- Insurance requirements

If the consultant suggests skipping any of these, **push back** and explain the legal exposure. These exist for compliance reasons, not bureaucratic preference.

### 5. Build the evaluation criteria

Read [`references/evaluation-patterns.md`](references/evaluation-patterns.md) and match the project to a pattern:

- **Price-dominant** (80/20 cost-quality): commodities, well-defined scope, low strategic risk
- **Balanced** (60/40 or 70/30): typical technology procurement
- **Quality-dominant** (50/50 or 40/60): consulting, professional services, novel domains

Define the sub-criteria within "quality" explicitly — proven experience (X years), key personnel CVs, methodology, references. Leave nothing to evaluator interpretation.

### 6. Vono house style

After the draft is complete, run a final pass against these rules:

- **No em dashes** (—). Use a regular hyphen with spaces or commas.
- **No emojis**.
- **Numbered lists** for any enumeration. Bulleted lists only for non-ordered concepts.
- **Tables** for comparing options or showing requirement → criterion → score mapping.
- **One topic per paragraph**. Long Hebrew paragraphs get skimmed and missed.
- **Define every acronym on first use**. "מערכת ה-CRM (ניהול קשרי לקוחות)".

### 7. Self-review checklist

Before handing the draft to the consultant, verify:

- [ ] Every mandatory clause from [`references/mandatory-clauses.md`](references/mandatory-clauses.md) is present.
- [ ] Threshold conditions (תנאי סף) are objectively measurable, not subjective.
- [ ] Evaluation criteria sum to 100%.
- [ ] Submission process specifies: format (PDF/sealed envelope/portal), deadline, required signatures, delivery address.
- [ ] Q&A timeline is set (typically: vendor questions due X, ministry responses due Y, both before submission).
- [ ] Schedule is realistic — never less than 21 days for vendor response on a non-trivial RFP.

## Output format

Present the RFP as a single document with:

1. **Cover page** — client name, RFP title, RFP number (placeholder if not yet assigned), date, contact person, submission deadline.
2. **Table of contents** — auto-generated from section headings.
3. **Body sections** — per the chosen template.
4. **Appendices** — declarations, forms, technical specs that don't fit in the body.

If the user asks for a single section only (e.g., "רק תנאי סף") — produce only that section, but flag what other sections must accompany it for the RFP to be valid.

## Why this matters

A well-written RFP saves three rounds of clarifications, reduces vendor disputes by an order of magnitude, and produces comparable proposals. A sloppy RFP creates legal risk for the client and weeks of follow-up work for the consultant. Treat every clause as if it will be cited in a future challenge — because it might be.
