# Vono Deliverable Types

Vono produces a small fixed set of deliverable types. Don't invent new ones. If you need a new type, talk to a senior consultant first.

## The seven core deliverables

### 1. One-pager
**Purpose**: Engagement scope on a single page
**When**: Day 1 of every engagement
**Length**: 1 A4 page
**Template**: see [`one-pager-template.md`](one-pager-template.md)

### 2. SOW (Statement of Work)
**Purpose**: Legal formalization of the one-pager
**When**: Before contracts signed
**Length**: 8-15 pages
**Sections**: Background, Scope, Deliverables, Schedule, Roles, Acceptance criteria, Commercial terms, Annexes

The SOW is the legal version of the one-pager. Anything that's in the one-pager must also be in the SOW. The SOW can have more detail; it cannot say something different.

### 3. Status report (weekly)
**Purpose**: Lightweight visibility into project health
**When**: Same day every week (Tuesday recommended)
**Length**: ≤1 page printed (or ≤400 words)
**Template**:

```markdown
# סטטוס שבועי - [שם הפרויקט]
**תאריך**: YYYY-MM-DD
**שבוע**: [N] מ-[total]

## סטטוס: 🟢 / 🟡 / 🔴
[משפט אחד שמסביר למה]

## מה ביצענו השבוע
- [3-5 עיקריים]

## מה הלאה
- [3-5 עיקריים]

## החלטות נדרשות
1. [החלטה], מ: [מאושר], עד: [תאריך]
   - אופציה 1: ...
   - אופציה 2: ...
   - המלצת Vono: ...

## סיכונים
- 🔴 [סיכון מהותי + mitigation]
- 🟡 [סיכון בינוני]

## נושאים פתוחים
- [נושא, אחראי, יעד פתרון]
```

### 4. Steering deck (bi-weekly)
**Purpose**: Strategic visibility for executive sponsor
**When**: Every 2 weeks, before the steering meeting
**Length**: ≤12 slides
**Structure**:

- **Slide 1**: סטטוס + headline 3-line summary
- **Slide 2**: החלטות נדרשות היום
- **Slides 3-N**: רקע לכל החלטה (אם נדרש)
- **Slide N+1**: עדכון תוכנית + milestone הבא
- **Slide N+2**: סיכונים מהותיים
- **Slide N+3** (אם רלוונטי): גרפים / metrics
- **Slide אחרון**: מתי נפגש שוב + מה לקרוא בינתיים

Don't overload slides. One idea per slide.

### 5. Phase-gate document
**Purpose**: Formal record of phase completion + sign-off
**When**: At the end of each phase
**Length**: Variable (Discovery memo: 5-10 pages; Design doc: 15-30 pages; etc.)

Each phase has a different deliverable. See [`lifecycle.md`](lifecycle.md) for what each phase produces.

Common structure:
1. Executive summary (1 page)
2. Phase goals + what we did
3. Findings / decisions
4. Recommendations for next phase
5. Risks updated
6. Sign-off page (printed, signed, scanned)

### 6. Recommendation memo
**Purpose**: Bring a specific decision to the client
**When**: When a decision is needed that's bigger than a status report can handle
**Length**: ≤2 pages

```markdown
# המלצה: [שם ההחלטה]
**תאריך**: YYYY-MM-DD
**Vono lead**: [שם]

## המלצה
[משפט אחד. ההמלצה. בלי hedging.]

## רקע
[2-3 משפטים. למה אנחנו צריכים החלטה.]

## אופציות שנשקלו
1. **אופציה א**: [תיאור קצר]
   - יתרונות: ...
   - חסרונות: ...
2. **אופציה ב**: [תיאור]
   - יתרונות: ...
   - חסרונות: ...
3. **אופציה ג** (המומלצת): [תיאור]
   - יתרונות: ...
   - חסרונות: ...

## המלצה מנומקת
[Vono ממליץ על אופציה ג כי...]

## סיכונים והפחתתם
- [סיכון 1] → [mitigation]
- [סיכון 2] → [mitigation]

## הצעד הבא
[מי, מה, מתי. בכתב.]
```

### 7. Final report
**Purpose**: Closing the engagement, capturing what we did + lessons learned
**When**: End of Stabilize phase
**Length**: 8-15 pages

```markdown
# דוח סיכום פרויקט - [שם הפרויקט]

## תקציר מנהלים (1 עמוד)
[מה עשינו, מה השגנו, מה ההמלצה הפתוחה]

## רקע ומטרות
[הצורך המקורי, מי הזמין, מה היה ה-baseline]

## מה עשינו
[פאזה אחר פאזה, בקצרה]

## תוצאות
### מה הצלחנו
- [תוצאה מדידה 1]
- [תוצאה מדידה 2]

### מה לא הצלחנו / נשאר פתוח
- [מה לא הושג, מה הסיבה, מה ההמלצה]

## הלקחים
- מה עבד שכדאי לחזור עליו
- מה לא עבד
- מה היינו עושים אחרת

## המלצות להמשך
- [מה הלקוח צריך לעשות בעצמו עכשיו, בלי Vono]
- [מה כדאי לחזור אלינו עוד 6 חודשים]

## נספחים
- [תוצרים מרכזיים]
- [Risk register סופי]
- [Stakeholder feedback - אם נאסף]
```

## Anti-deliverables (don't produce these)

### "Status update" of more than 1 page
If your status update is 5 pages, you're hiding something or you're not filtering. The senior client won't read it. Cut.

### Slide deck of 40 slides for a steering meeting
Long decks signal you don't know what's important. Cap at 12. If you need more, you're using the wrong meeting type.

### Verbal-only deliverables
Every deliverable is in writing. "We discussed it in the meeting" is not a deliverable.

### Boilerplate-heavy proposals
Avoid copy-pasted background paragraphs that add no value. Every paragraph in a Vono document earns its place.

### "Detailed work plan" that's a 200-row Gantt chart
Detailed Gantt charts give false confidence. Use phase milestones in the one-pager + a working tracker (separate from client deliverables).

## When in doubt

Pick the smallest deliverable that does the job. If a status report is enough, don't write a recommendation memo. If a recommendation memo is enough, don't write a phase-gate document.

The senior client respects brevity. The mistake to avoid: producing more documents than the engagement needs.
