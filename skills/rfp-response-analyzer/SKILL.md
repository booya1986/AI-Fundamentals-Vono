---
name: rfp-response-analyzer
description: Use this skill whenever a consultant needs to analyze, score, or compare vendor responses to an Israeli public-sector RFP (מכרז). Trigger when the user has the original RFP plus 2 or more vendor proposals and wants a comparison matrix, gap analysis, threshold-condition verification, or a scored ranking. Trigger even if the user says things like "תעבור על ההצעות", "תשווה בין הספקים", "תכין טבלת השוואה", "תבדוק עמידה בתנאי סף", or "תנקד את ההצעות". The skill encodes Vono's evaluation methodology, mandatory verification steps (תנאי סף, אישורים, ערבויות), the comparison-matrix template, and red/yellow/green flagging for risk areas. This is the natural pairing for the `rfp-writer` skill.
---

# RFP Response Analyzer (Vono / Israeli Public Sector)

This skill helps a Vono consultant evaluate vendor responses to an RFP — verifying compliance, building comparison matrices, and producing a scored ranking that the client's evaluation committee can act on.

## When to use

Use this skill when the user supplies:
- The original RFP (or a summary of its key requirements)
- Two or more vendor responses (full PDFs or text extracts)

And asks for any of:
- A side-by-side comparison
- Threshold-condition verification (תנאי סף)
- Gap analysis against the requirements
- A scored ranking per the published evaluation criteria
- Red/yellow/green risk flagging

Do NOT use this skill for:
- Writing new RFPs (use `rfp-writer`).
- Single-vendor reviews where there's nothing to compare against (use it anyway, but note that scoring becomes meaningless without a comparison set).
- Evaluating commercial proposals outside the public-sector framework.

## Workflow

### 1. Establish the evaluation framework

Before analyzing anything, lock down these three things from the RFP:

1. **תנאי סף (threshold conditions)** — list every absolute requirement. Failure on any single one means automatic disqualification, regardless of how good the rest of the response is.
2. **אמות מידה לבחירה (scoring criteria)** — the published weights (e.g., 70/30 cost-quality with sub-weights). Don't invent your own.
3. **דרישות פונקציונליות / לא-פונקציונליות** — extract the numbered requirements that vendors had to address. If they're called `F-001`, `F-002`, etc., use those identifiers throughout the analysis.

If the RFP isn't fully available, ask the user for the threshold conditions and scoring weights at minimum. Don't proceed without them.

### 2. Threshold-condition verification (תנאי סף)

Read [`references/threshold-checks.md`](references/threshold-checks.md) for the full standard checklist.

For each vendor, produce a binary pass/fail table:

```
| תנאי סף                        | ספק א | ספק ב | ספק ג |
|-------------------------------|-------|-------|-------|
| אישור ניהול ספרים תקף         |  ✓   |  ✓   |  ✗   |
| ערבות מכרז 250,000 ₪          |  ✓   |  ✓   |  ✓   |
| ניסיון: 3+ פרויקטים דומים      |  ✓   |  ✗*  |  ✓   |
| תעודת ISO 27001 תקפה          |  ✓   |  ✓   |  ✗   |
```

Any `✗` in this table means **automatic disqualification**. Flag it explicitly and recommend the consultant verify with a phone call before issuing a formal disqualification — sometimes the document is missing but the certification exists.

Mark borderline cases with `✗*` and a footnote:
- "ספק ב' הציג 2 פרויקטים בהיקף הנדרש ופרויקט שלישי בהיקף 80% מהדרישה - דרושה החלטת ועדה."

### 3. Build the requirements-coverage matrix

Read [`references/comparison-matrix-template.md`](references/comparison-matrix-template.md).

For each numbered requirement (`F-001`, `NFR-005`, etc.), capture:

- **כיסוי** — מלא / חלקי / לא נענה
- **ציטוט** — שורה אחת מההצעה שמוכיחה את התשובה (עם מספר עמוד/סעיף)
- **הערה** — אם יש סייג, התניה, או חוסר בהירות

Don't paraphrase the vendor's wording when checking coverage — copy the actual sentence. Vendors will later challenge a paraphrase that loses nuance.

If a vendor says "נתמוך בעברית מלאה" but doesn't specify RTL handling for forms, mark coverage as **חלקי** with a note. Don't give credit for vague intent.

### 4. Score per the published criteria

Apply the RFP's scoring formulas exactly. Read [`references/scoring-methods.md`](references/scoring-methods.md) for the standard formulas (יחסי, מוחלט, formulas for cost components).

For each vendor produce:

```
ספק א'
- ניקוד מחיר:           58.4 / 70  (הצעה: 4.2M ₪, נמוך ביותר: 3.5M)
- ניסיון מוכח:           9 / 10    (5 פרויקטים מתוכם 4 בתחום)
- CV של אנשי המפתח:      8 / 10    (ראש צוות 12 שנים, חבר צוות מפתח 8 שנים)
- מתודולוגיה:            7 / 10    (Discovery + Build, חסר phase למידה)
- ──────────────────────
- סה"כ:                 82.4 / 100
```

Show the math. The client's evaluation committee needs to defend the score if challenged.

### 5. Risk flags (red/yellow/green)

For each vendor, provide a final risk summary using these categories:

- 🟢 **ירוק** — אין חששות מהותיים. ניתן להתקדם בביטחון.
- 🟡 **צהוב** — חששות נקודתיים שדורשים בירור / clarification מהספק לפני המלצה.
- 🔴 **אדום** — בעיות מהותיות. גם אם הניקוד גבוה, יש סיכון מבני בהתקשרות.

Flags are based on patterns in [`references/risk-flags.md`](references/risk-flags.md):
- מחיר נמוך מ-30% מהאומדן (סיכון underbid)
- היעדר references בתחום הספציפי
- צוות ראשי שלא צוין בהסכם בלעדיות
- אי-התאמה בין NFR לארכיטקטורה המוצעת
- exposure לסיכון עסקי של הספק (חברה בקשיים, מיזוג קרוב)

### 6. Final deliverable

Present results in this exact structure:

1. **Executive summary** — שורה אחת לכל ספק, ניקוד סופי, דגל סיכון, המלצת ועדה
2. **Threshold conditions table** — pass/fail מטריצה
3. **Scoring breakdown** — לכל ספק, פירוט הניקוד לפי הקריטריונים
4. **Coverage matrix** — דרישות פונקציונליות ולא-פונקציונליות (לרוב נספח)
5. **Risk analysis** — התראות אדומות וצהובות, עם הצעות mitigation
6. **Recommendation** — דירוג מסודר + הסבר למה (לא רק ציון)

## Output formatting

- **Tables** for everything that can be tabulated. Vendors and committees need to scan, not read.
- **Direct quotes** from vendor responses, with page number references (`עמ' 14, סעיף 3.2.1`). Never paraphrase critical claims.
- **Numbered findings** — ייקל על המכותבים להפנות לסעיפים בדיון הוועדה.
- **Hebrew throughout** — אם ההצעה באנגלית, צטטו במקור והוסיפו הערת תרגום.

## Vono house rules

### Never invent

If a vendor didn't address a requirement, write **"לא נענה"**. Don't guess what they probably meant. The vendor missed the requirement — that's data.

### Cross-check the numbers

Vendors sometimes contradict themselves between sections. If section 4 says "5 שנים ניסיון" and section 7 says "8 שנים", flag it. Pick the lower number for scoring and note the inconsistency.

### Reference page numbers

Every claim in your analysis should be traceable. `(עמ' 23, סעיף 4.5.2)` after each finding. The committee will thank you when a vendor disputes a score.

### Sealed-bid integrity

If you're working on a live tender (not a post-analysis exercise), follow these rules:
- Don't share interim findings with one vendor before the others.
- Don't compare prices openly until the official price-opening session.
- All clarification questions go through the official channel, never bilaterally.

## Why this matters

A sloppy vendor analysis costs the client months of rework and exposes them to legal challenges. Every gap you miss becomes a future change request at 3× the price. Every threshold condition you fail to verify creates audit risk. Treat the analysis as if it will be quoted in a court filing — because if there's a challenge, it will be.
