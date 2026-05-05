# Vono One-Pager Template

The one-pager is the core of every engagement. It fits on a single A4 page (printed). If it doesn't fit on one page, the engagement isn't well-defined yet.

## Template

```
╔══════════════════════════════════════════════════════════╗
║                                                          ║
║  PROJECT NAME / שם הפרויקט                              ║
║  Client / לקוח: [name]                                   ║
║  Date / תאריך: [YYYY-MM-DD]                              ║
║  Owner / אחראי Vono: [single name]                       ║
║                                                          ║
╠══════════════════════════════════════════════════════════╣
║                                                          ║
║  1. WHY (למה)                                            ║
║  [One paragraph. The business problem we're solving and  ║
║   why now. Not "the client wants X" but the underlying   ║
║   business reason.]                                      ║
║                                                          ║
║  2. WHAT (מה)                                            ║
║  [One sentence. The deliverable. Concrete and verifiable.]║
║                                                          ║
║  3. WHO (מי)                                             ║
║  - Vono lead: [name, role]                               ║
║  - Vono team: [N people, roles]                          ║
║  - Client sponsor: [name, role] - decision authority    ║
║  - Client business owner: [name, role] - day-to-day     ║
║  - Client tech lead: [name, role] (if applicable)       ║
║                                                          ║
║  4. WHEN (מתי)                                           ║
║  Phase 1 - Discovery: [date - date]                     ║
║  Phase 2 - Design:    [date - date]                     ║
║  Phase 3 - Build:     [date - date]                     ║
║  Phase 4 - Deploy:    [date - date]                     ║
║  Phase 5 - Stabilize: [date - date]                     ║
║  Final delivery:      [date]                            ║
║                                                          ║
║  5. WHAT WE NEED FROM YOU (מה אנחנו צריכים)              ║
║  - [Specific access, e.g., "Read access to current CRM"]║
║  - [Stakeholder availability, e.g., "5 hours/week of    ║
║     business owner time"]                                ║
║  - [Decision authority, e.g., "Authority to commit on   ║
║     budget items < 100K NIS"]                           ║
║  - [Information, e.g., "Current process docs in week 1"]║
║                                                          ║
║  6. OUT OF SCOPE (מה לא בתוכנית)                         ║
║  - [Explicit exclusions]                                 ║
║  - [Things the client might assume but aren't covered]  ║
║                                                          ║
║  7. SUCCESS CRITERIA (איך נדע שהצלחנו)                   ║
║  - [Measurable outcome 1]                                ║
║  - [Measurable outcome 2]                                ║
║  - [Measurable outcome 3]                                ║
║                                                          ║
║  8. COST                                                 ║
║  [Total fee, payment terms, what's included]             ║
║                                                          ║
╚══════════════════════════════════════════════════════════╝
```

## Section-by-section guidance

### 1. WHY

Not "the client wants a CRM". Not "ה-CIO ביקש". The actual underlying business problem.

Good: *"רכש בנקאי מבוצע באמצעות שאלוני Word של 80 עמ' ופגישות 1-on-1 עם ספקים. תהליך זה לוקח 4-6 חודשים, אנחנו מאבדים ספקים חזקים, ועלות פנימית גבוהה. הפרויקט נועד לקצר את התהליך ל-6-8 שבועות תוך שמירה על איכות ההחלטה."*

Bad: *"לכתוב תוכנית עבודה למערכת CRM."*

### 2. WHAT

A single sentence that describes the deliverable concretely. If you can't say it in one sentence, the project isn't well-defined yet.

Good: *"מערכת RFP פנימית מבוססת Claude Project + Custom GPT + תהליך ייעוץ תמיכה למשך 3 חודשים."*

Bad: *"שיפור תהליכי הרכש."*

### 3. WHO

Each row has a single name, not a department or "the team". If you don't know the names, get them before signing the SOW.

The four canonical roles:
- **Vono lead** — accountable for project delivery
- **Client sponsor** — funds the engagement, has the political weight
- **Client business owner** — day-to-day partner, business expertise
- **Client tech lead** — system/IT expertise (if technology is involved)

If two of these are the same person (e.g., sponsor + business owner), note it. If three are the same person, the project is at risk of failing because that person becomes a single point of failure.

### 4. WHEN

Phase milestones, not Gantt details. The detailed schedule lives in the SOW.

Five rows, one per phase. Date ranges or fixed dates.

If the user is asking for a project timeline shorter than 4 weeks, push back unless scope is genuinely tiny. Compression below that is reckless.

### 5. WHAT WE NEED FROM YOU

The client always commits more than they realize. List explicitly:
- **Access** (read/write to systems)
- **People time** (hours per week of which roles)
- **Decision authority** (who can decide what, what's the threshold)
- **Information** (documents, data, prior project history)

This list prevents the most common project killer: "we needed X but you didn't tell us, so it took 3 weeks to get".

### 6. OUT OF SCOPE

Explicitly list what's NOT included. The client will assume things are in scope unless told otherwise.

Common things to put here:
- Training (if the project is delivery only)
- Ongoing support beyond Stabilize phase
- Integration with systems not named in scope
- Custom development beyond X hours
- Migration from prior tooling

### 7. SUCCESS CRITERIA

Measurable. Not "client satisfaction" — specific KPIs.

Good:
- "RFP cycle time drops from 4-6 months to 6-8 weeks (measured by 3 RFPs completed in pilot)"
- "Adoption: 80% of new RFPs use the new tool by end of Stabilize"
- "Cost saving: -50% internal hours per RFP (measured against baseline survey)"

Bad:
- "Client is happy"
- "מערכת איכותית"
- "תהליך משופר"

### 8. COST

The total. Payment milestones (e.g., "30% on signature, 30% on Design approval, 40% on Stabilize").

Be explicit about what's included:
- Labor only? Materials? Subcontractor fees?
- Travel? T&E?
- Add-ons that may emerge?

## Use of the one-pager

### Internal alignment
Before sending to the client, walk the Vono team through the one-pager. Anyone who doesn't understand the WHY is missing alignment.

### Client co-creation
Don't write it alone and present. Write a draft, send it, then walk through it together. The client may push back on success criteria, scope, or timeline. Better to discover that now than in week 4.

### Reference document
Keep the one-pager visible throughout the engagement. At every steering meeting, at every phase gate, ask: "Are we still building toward this?"

### Updates require sign-off
If the project changes (scope, timeline, success criteria), update the one-pager and get re-signature. Verbal "yeah, we agreed to expand scope" is not sufficient.

## Pattern

The one-pager is the engagement contract.
The SOW is the legal formalization.
The phase gates are the checkpoints.
Every status report points back to the one-pager.

If during the engagement someone says "wait, what are we building?", the answer is the one-pager. If the one-pager doesn't answer, the one-pager isn't good enough.
