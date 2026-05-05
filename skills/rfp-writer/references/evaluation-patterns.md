# Evaluation Criteria Patterns

Three canonical patterns for distributing weight between price and quality. Pick the pattern that matches the procurement risk profile.

## Pattern 1 — Price-dominant (80/20)

**When to use**: commodities, fungible services, well-defined scope where vendors compete primarily on cost.

Examples: cloud-hosting renewal, hardware refresh, standard licenses, cleaning services.

```
מחיר:    80%
איכות:   20%
   ├── ניסיון מוכח      8%
   ├── זמני אספקה        7%
   └── מענה לדרישות      5%
```

Risk: in technology, this often produces a winner who can't actually deliver. Avoid for anything with implementation complexity.

## Pattern 2 — Balanced (60/40 or 70/30)

**When to use**: typical IT system procurement — known requirements, several capable vendors, real implementation work.

Examples: CRM/ERP rollout, BI platform, infrastructure modernization.

### 70/30 variant (lower complexity)

```
מחיר:    70%
איכות:   30%
   ├── ניסיון מוכח (3+ פרויקטים דומים)        10%
   ├── רמת ה-CV של אנשי המפתח               7%
   ├── מתודולוגיית הטמעה                    7%
   └── עמידה בדרישות לא-פונקציונליות (NFR)  6%
```

### 60/40 variant (higher complexity)

```
מחיר:    60%
איכות:   40%
   ├── ניסיון בתחום ספציפי                  10%
   ├── רמת ה-CV של אנשי המפתח               10%
   ├── מתודולוגיה והטמעה                    8%
   ├── הצעה טכנית (אופציונלי - ארכיטקטורה)  6%
   └── הוכחת רעיון / POC (במכרזים מורכבים)  6%
```

## Pattern 3 — Quality-dominant (50/50 or 40/60)

**When to use**: consulting, professional services, strategy work, novel domains, anywhere the WHO matters more than the WHAT.

Examples: digital transformation strategy, change management, executive-coaching programs, niche technical consulting.

### 50/50 variant

```
מחיר:    50%
איכות:   50%
   ├── ניסיון מוכח של החברה                 10%
   ├── רמת ה-CV של ראש הצוות (מינ' 10 שנים) 15%
   ├── רמת ה-CV של חברי הצוות               10%
   ├── מתודולוגיה מוצעת                     10%
   └── המלצות מלקוחות בעלי פרופיל דומה        5%
```

### 40/60 variant (strategy / very specialized)

```
מחיר:    40%
איכות:   60%
   ├── ניסיון בתחום הספציפי                 15%
   ├── ראש צוות (CV + ראיון)                20%
   ├── מתודולוגיה ותפיסת עבודה               10%
   ├── תוצרים ומסמכי דוגמה מפרויקטים קודמים 10%
   └── ראיונות / מצגת לוועדה                 5%
```

## Sub-criteria definitions

### "ניסיון מוכח" — never leave this vague

Specify exactly:
- **כמה פרויקטים?** "לפחות 3 פרויקטים בהיקף [X] ש"ח שבוצעו ב-5 השנים האחרונות"
- **באיזה תחום?** "מערכות CRM לגופי בריאות בישראל" — not "מערכות מסחריות"
- **איך מוכיחים?** "מסמכי סיום פרויקט חתומים על ידי הלקוח" - not "תיאור הפרויקט"

### "רמת ה-CV"

Specify exactly:
- **מי נדרש?** ראש צוות + מספר חברי צוות מפתח (מנתח מערכת, ארכיטקט, מומחה אבטחה, וכו')
- **כמה שנים?** טווחים מובהקים: "ראש צוות - 10+ שנים, חברי צוות - 5+ שנים"
- **באילו תחומים?** הסמכות פורמליות (PMP, ITIL, CISA, וכו')
- **באיזה מודל ניקוד?** מוחלט (X שנים = Y נקודות) או יחסי (הספק הטוב ביותר מקבל מקסימום)

### "מתודולוגיה"

Specify what the vendor must demonstrate:
- **תוצרים בכל שלב** — Discovery → Design → Build → Test → Deploy
- **מנגנוני בקרה** — איך הלקוח רואה התקדמות, מאשר phases
- **ניהול סיכונים** — מתודולוגיה מוכרת או בית-יד
- **תקשורת** — מבנה ותדירות של פגישות steering, status reports

## Scoring methods

### יחסי (Relative scoring) — most common

```
ניקוד הספק = (ערך הספק / הערך הטוב ביותר במכרז) × ניקוד מקסימלי
```

Example: בקריטריון "ניסיון" שמשקלו 10 נקודות, ספק עם 5 פרויקטים מקבל את המקסימום, ספק עם 3 פרויקטים מקבל 6 נקודות (3/5 × 10).

### מוחלט (Absolute scoring)

לכל סף - ניקוד קבוע:
- 0-2 פרויקטים: 0 נקודות (פסילה)
- 3-4 פרויקטים: 5 נקודות
- 5-7 פרויקטים: 8 נקודות
- 8+ פרויקטים: 10 נקודות

Use when: דרישת רף מינימלי + תמריץ לעודף.

### Cost component formulas

Standard formula:
```
ניקוד מחיר = (המחיר הנמוך ביותר / מחיר ההצעה) × ניקוד מקסימלי
```

⚠️ **Watch out for outlier-low bids**: ספק שמציע 1 ש"ח יקבל את כל הניקוד והשאר יקבלו אפס. הוסיפו clause:
> *"הוועדה רשאית לפסול הצעה הנמוכה ביותר מ-30% מהאומדן ללא הסבר משכנע."*

## Quick decision matrix

| מצב | תבנית מומלצת |
|-----|--------------|
| Commodity, סטנדרטי, סקופ ברור | 80/20 |
| מערכת IT עם הטמעה, בינוני בסיכון | 70/30 |
| מערכת IT מורכבת, integration-heavy | 60/40 |
| Implementation services / consulting | 50/50 |
| Strategy / pure consulting / niche | 40/60 |

## Vono house default

When in doubt and the procurement is a system + implementation hybrid: **start with 65/35** and adjust based on client risk tolerance.
