# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Single-file Hebrew/RTL HTML slide deck for the Vono workshop ("AI Fundamentals @ Vono"). Built off the same template family as the Poalim and Remotion-Tutorial decks. ~40 slides, dark theme, brand-green neon (`#22C55E` / `#4ade80`).

## Files

- `index.html` — the entire deck (HTML + inline `<style>` + inline `<script>`). ~3600 lines.
- `assets/avi.png` — clean cutout of the presenter, used in slide 2 (About).
- `assets/image.webp` — Aviv Madar (Vono founder) photo with NERF guns (transparent cutout), used in the closing-quote slide. WebP with alpha; encoded via `cwebp -q 85 -alpha_q 100 -resize 1200 0`.
- `assets/favicon.png` — site favicon (256×256 crop of avi.png).
- `assets/screenshots/` — slide screenshots used by the README and as the OG share image.
- `skills/` — three Claude Skills shareable with the Vono team: `rfp-writer`, `rfp-response-analyzer`, `vono-methodology`. Each is a folder with `SKILL.md` + `references/` markdown files. Self-contained from the deck — they live in the same repo so the team can clone-and-share, but they don't depend on or reference the deck.

There is no build step, no package manager, no tests. To preview, open `index.html` directly in a browser:

```bash
open index.html      # macOS
```

## Architecture

### Slide model

Every slide is a `<section class="slide" data-layout="<type>" data-title="...">` inside the single `<div class="slideshow">` container. Only the slide with class `active` is visible; transitions are CSS opacity/transform on `.exit-left` / `.exit-right`.

`data-title` is the Hebrew title used by the dot-nav tooltip and aria-live announcements. `data-layout` selects which CSS rules apply.

### Layouts (data-layout values, all defined in the inline `<style>`)

`title` `about` `yesno` `big-question` `divider` `stat` `quote` `compare` `timeline` `tokens` `probability` `cards` `badgood` `demo` `content` `centered` `process` `pillars` `statement` `cta` `socials` `person-quote`

To add a slide, pick the closest layout and copy the structure of an existing slide that uses it. Layout-specific CSS lives next to its layout block in the `<style>` section.

### Citation slides (the Poalim hierarchy)

Quote slides that cite an article (`HBR`, `WEF`, `MCKINSEY`, `DELOITTE`, `GARTNER`, plus Aviv) follow this exact order — match it when adding new ones:

1. `<span class="quote-watermark">XXX</span>` — large faded letters in the bottom-right corner
2. `<div class="quote-source">SOURCE · DATE</div>` — small uppercase neon-green label at the top
3. `<div class="quote-text">…<mark>highlighted</mark>…</div>` — light-weight body, `max-width: 820px`
4. `<div class="article-links"><a class="article-link">…</a></div>` — subtle rectangular gray link

Stat slides (78%, 88/11, 40%) use the same quote layout — the percentage just sits inside `<mark>` in the quote text. Do **not** revive the old `.stat-takeaway` block (the green-bordered side-bar takeaway) — Avi rejected it.

### Navigation chrome (built once at script bottom)

- `#dotNav` — auto-built from the slide list; the active dot expands and shows the slide number (`01`, `02`, …)
- `#prevBtn` / `#nextBtn` — circular nav buttons. RTL convention: prev points `›` (right) and sits on the right; next points `‹` (left) and sits on the left. Do not flip the SVGs.
- `#scCurrent` / `#scTotal` — top-left counter (`01 / 40`)
- `#fullscreenBtn` — toggles `document.fullscreen`, also bound to `F` key
- `#progressBar` — green strip that fills as you advance
- `#keyboardHint` — `[←] [→] [Space]` chips + `לניווט`, fades after 6s
- Keyboard: ArrowLeft = next, ArrowRight = prev (RTL), Space/PageDown = next, PageUp = prev, Home/End, F for fullscreen
- Touch: swipe left advances (RTL-correct)

### Share-link / SEO

The `<head>` block carries Open Graph + Twitter Card meta tags pointing at `assets/screenshots/slide-01-title.png` (1920×1080). When the URL is pasted into Slack/WhatsApp/Twitter, the preview shows the title slide. If you swap the title slide visual significantly, regenerate the screenshot via the Playwright MCP (capture viewport at 1920×1080) and overwrite `assets/screenshots/slide-01-title.png` — the OG meta points to the live URL of that file.

### Animations

All `@keyframes` animations are wrapped in `@media (prefers-reduced-motion: reduce)` overrides at the bottom of the `<style>` block. When adding a new animation, add a corresponding `animation: none;` rule there. Currently guarded: `.slide::before` (gridDrift), `.about-smoke .smoke` (smokeDrift), `.demo-blink`/`.cta-meta-item .pulse` (blink), `.slide[data-layout="probability"] .prob-fill` (probFill), `.cw-token` (cwFlow), `.cards-grid > .content-card` and `.players-row > .player` (cardEntry stagger), `.statement-text` and `.statement-text mark` (statement reveal).

**Slide-entry choreography (added in polish pass):**

- **Card stagger** — every `.cards-grid` slide and the `.players-row` players slide stagger their children in via `cardEntry` keyframes, with `nth-child(1..14)` setting `animation-delay` (~0.05–0.97s). Adds depth without changing layout.
- **Statement reveal** — slide 18 (`data-layout="statement"`) keeps `.statement-text` muted gray for 300ms, then fades to heading color while the inner `<mark>` (the climax phrase) does a `markReveal` keyframe: scale 1 → 1.06 → 1 with a green glow. Drives the eye to the key phrase.
- **Probability bars** — `.prob-fill` uses CSS variable `--w` (e.g. `style="--w: 62%;"`) and animates from 0 to `var(--w)` with stagger via `nth-child` delays.
- **Count-up for `<mark>` percentages** — JS at the bottom of `<script>` watches every slide's `.active` class via `MutationObserver`. When a slide becomes active, it inspects each `<mark>` and if the text matches `/^(\d+)(%?)$/`, animates it from 0 to the target value over ~600–1400ms. The dataset (`data-counted-target`, `data-counted-suffix`) is cached so re-entry replays the animation. Runs only when `prefers-reduced-motion` is not set.

### CSS conventions (deck-wide)

- Brand tokens at `:root`: `--accent`, `--accent-light`, `--bg`, `--text-heading`, `--text-body`, `--text-muted`
- All decorative card/content icons are inline SVG (`stroke="currentColor"`, `fill="none"`, `stroke-width="1.5"`, `stroke-linecap="round"`) with a green neon glow via `filter: drop-shadow(...)`. **Never use emojis or Unicode glyphs** as card icons — Avi specifically rejected this and the rule is documented in his memory file.
- `.content-card` is a CSS Grid: `"icon title" / "desc desc"`. Icon and title share the top row, description spans both columns below.
- `.card-title` and `.card-desc` are `text-align: right` (RTL). The `.card-desc` rule is intentionally written as `.slide p.card-desc, .card-desc {…}` because `.slide p { text-align: center }` would otherwise win on specificity.
- The default `.slide` background is a green radial gradient. The Aviv quote slide uses `data-layout="quote"` so it inherits everything correctly — don't add stronger gradients on stat/quote layouts (Avi pushed back on amplification).
- "Project level" badges (slide "הפרויקטים שלכם") use `.lvl-1` (green = easy), `.lvl-2` (cyan #38BDF8 = medium), `.lvl-3` (orange #FB923C = advanced). The colored chips on the prompting slide (`[ROLE]` etc.) use the same five-color palette via CSS variables.
- The projects grid (14 cards) uses a virtual 6-column layout with each card spanning 2 columns. Cards 13–14 are explicitly placed (`grid-column: 2 / span 2` and `4 / span 2`) so the last row centers two cards on a row of three instead of orphaning them. The selectors guard with `:nth-last-child(N):nth-child(M)` so the centering only triggers when total = 14.

### Em dashes are banned

Avi removed all `—` from the deck and prefers regular hyphens. When adding text don't reintroduce em dashes.

### Slide order at a glance

Title → About (`avi.png`) → Yes/No → Icebreaker → Part 2 (state of orgs: 78% / 88-11% / 40% / HBR / WEF / WEF / Deloitte / 56% / Compare) → Timeline (Gen-AI history) → Summary → Part 4 (mental model: Statement / Tokens / Probability / Attention / 5 behaviors / Hallucinations) → Part 5 (live demo: setup / summary) → Part 6 (Players / Practical truth) → Part 7 (5 concepts: Context / Prompt / RAG / Reasoning / Tool Use) → Tool Matrix → Part 9 (divider / Auto-vs-Agent) → Projects (14 cards, last 2 centered) → **Aviv quote (penultimate)** → Socials (last).

If you reorder, the dot-nav and counter rebuild automatically from the DOM order — no JS changes needed.
