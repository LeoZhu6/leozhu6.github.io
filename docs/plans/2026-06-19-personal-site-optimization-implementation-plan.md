# Personal Site Optimization Implementation Plan

> **For Hermes:** Use subagent-driven-development skill to implement this plan task-by-task.

**Goal:** Redesign the static personal website into a biotech-finance builder dossier while preserving factual accuracy and existing static deployment simplicity.

**Architecture:** Keep the site as a single static `index.html` with local image assets. Make surgical edits to CSS tokens, section order, content blocks, accessibility states, metadata, and image attributes. Do not introduce a framework or build step.

**Tech Stack:** Static HTML, CSS, vanilla JavaScript, local Python HTTP server for verification, browser visual inspection.

---

## Confirmed Inputs

- Project root: `D:\Project\personal-site`
- Main file: `index.html`
- Design spec: `docs/superpowers/specs/2026-06-19-personal-site-optimization-design.md`
- BioMarket Tracker live link: `https://runze-bio-market-tracker.streamlit.app/`
- LinkedIn: `https://www.linkedin.com/in/runze-zhu-8143b4380/`
- BioMarket Tracker GitHub link: do **not** add to the site.
- Tencent Ads: keep high-level only; no specific/confidential project details.
- CGA/GPA source: attached resume/transcript; use `3.856 / 4.3` consistently if CGA appears.
- Visual palette: biotech sage green + muted copper.

---

## Task 1: Add SEO and social metadata

**Objective:** Improve page preview and search snippet without changing visible layout.

**Files:**
- Modify: `index.html:3-10`

**Steps:**

1. Add these tags inside `<head>` after the viewport tag:

```html
<meta name="description" content="Runze Zhu is an HKUST BBA student studying Finance and BioEngineering, building AI-driven biotech market analytics tools and working across healthcare investment banking, venture research, and platform strategy.">
<meta property="og:title" content="Runze Zhu — Biotech Finance Builder">
<meta property="og:description" content="Finance, biotechnology, and AI-driven research workflows — from healthcare M&A case decks to BioMarket Tracker.">
<meta property="og:type" content="website">
<meta property="og:url" content="https://leozhu6.github.io/">
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Runze Zhu — Biotech Finance Builder">
<meta name="twitter:description" content="HKUST BBA student building at the intersection of biotech finance and AI analytics.">
```

2. Update title to:

```html
<title>Runze Zhu — Biotech Finance Builder</title>
```

3. Verify:

```bash
grep -n "description\|og:title\|twitter:title\|<title>" index.html
```

Expected: all new metadata appears once.

4. Commit:

```bash
git add index.html && git commit -m "feat: add personal site metadata"
```

---

## Task 2: Update visual tokens and accessibility motion handling

**Objective:** Shift the site from generic warm orange to biotech finance green/copper and improve motion accessibility.

**Files:**
- Modify: `index.html:14-28`
- Modify: `index.html` CSS responsive/accessibility area near the end of `<style>`

**Steps:**

1. Replace current color tokens with:

```css
--bg:           #FAF8F2;
--bg-warm:      #F1ECE2;
--bg-dark:      #25251F;
--bg-mid:       #E8E0D3;
--ink:          #191714;
--ink-60:       rgba(25,23,20,0.62);
--ink-40:       rgba(25,23,20,0.42);
--ink-20:       rgba(25,23,20,0.12);
--accent:       #4A7C59;
--accent-warm:  #B66A3C;
--accent-dim:   rgba(74,124,89,0.12);
--snow:         #ffffff;
--border:       rgba(25,23,20,0.12);
```

2. Add focus styles near base styles:

```css
a:focus-visible,
button:focus-visible {
  outline: 2px solid var(--accent);
  outline-offset: 4px;
}
```

3. Add reduced-motion CSS before the closing `</style>`:

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation: none !important;
    transition: none !important;
    scroll-behavior: auto !important;
  }
}
```

4. Verify:

```bash
grep -n "#4A7C59\|prefers-reduced-motion\|focus-visible" index.html
```

Expected: all three patterns appear.

5. Commit:

```bash
git add index.html && git commit -m "feat: update visual tokens and motion accessibility"
```

---

## Task 3: Rewrite Hero content and proof strip

**Objective:** Make the first screen communicate the biotech-finance builder identity immediately.

**Files:**
- Modify: `index.html:1321-1355`

**Steps:**

1. Replace the hero label/title/subtitle with:

```html
<p class="hero-label">HKUST Business School · Finance × BioEngineering</p>
<h1 class="hero-title">
  Biotech finance,<br>
  <em>translated into investable insight.</em>
</h1>
<p class="hero-sub">
  I study Finance &amp; BioEngineering at HKUST and build AI-driven research workflows
  for biotech markets, healthcare investing, and platform strategy.
</p>
```

2. Replace the current three hero stats with four proof points:

```html
<div class="hero-stats hero-stats--proof">
  <div class="hero-stat">
    <span class="hero-stat-val">HKUST BBA</span>
    <span class="hero-stat-lbl">Finance × BioEngineering</span>
  </div>
  <div class="hero-stat">
    <span class="hero-stat-val">Healthcare IB</span>
    <span class="hero-stat-lbl">Haoyue Capital</span>
  </div>
  <div class="hero-stat">
    <span class="hero-stat-val">Top 10 / 90</span>
    <span class="hero-stat-lbl">VCOC Investment Challenge</span>
  </div>
  <div class="hero-stat">
    <span class="hero-stat-val">Live Product</span>
    <span class="hero-stat-lbl">BioMarket Tracker</span>
  </div>
</div>
```

3. Replace CTA labels:

```html
<a href="#selected-work" class="btn-primary">View selected work</a>
<a href="https://runze-bio-market-tracker.streamlit.app/" target="_blank" rel="noopener" class="btn-text">
  Launch BioMarket Tracker
  ...existing svg...
</a>
```

4. If the four proof points are cramped, add mobile-friendly wrapping:

```css
.hero-stats--proof {
  flex-wrap: wrap;
}
```

5. Verify:

```bash
grep -n "Biotech finance\|selected-work\|Top 10 / 90\|Launch BioMarket Tracker" index.html
```

Expected: all patterns appear.

6. Commit:

```bash
git add index.html && git commit -m "feat: sharpen hero positioning"
```

---

## Task 4: Add Selected Work CSS

**Objective:** Add styles for a new artifact-led section before moving content.

**Files:**
- Modify: `index.html` CSS after Projects or Experience section styles

**Steps:**

1. Add CSS classes for `.selected-work-grid`, `.work-card`, `.work-card--featured`, `.work-card-label`, `.work-card-title`, `.work-card-desc`, `.work-card-meta`, `.work-card-visual`, and `.work-card-actions`.

2. Reuse existing color, typography, tag, and card patterns. Keep the implementation minimal; do not duplicate large blocks unnecessarily.

3. Required behavior:

```css
.selected-work-grid {
  display: grid;
  grid-template-columns: 1.15fr 0.85fr;
  gap: 1px;
  background: var(--border);
  border: 1px solid var(--border);
  border-radius: 10px;
  overflow: hidden;
  margin-top: var(--sp-48);
}

.work-card {
  background: var(--bg-warm);
  padding: var(--sp-40);
}

.work-card--featured {
  background: var(--bg-dark);
  color: var(--snow);
}

@media (max-width: 860px) {
  .selected-work-grid { grid-template-columns: 1fr; }
}
```

4. Verify:

```bash
grep -n "selected-work-grid\|work-card--featured" index.html
```

Expected: styles exist once.

5. Commit:

```bash
git add index.html && git commit -m "feat: add selected work styles"
```

---

## Task 5: Insert Selected Work section after Hero

**Objective:** Surface the strongest artifacts within the first two scrolls.

**Files:**
- Modify: `index.html` after `</section>` closing the Hero and before `<!-- About -->`

**Steps:**

1. Insert a new section with id `selected-work`.

2. Include three cards:

- BioMarket Tracker
  - Link only to `https://runze-bio-market-tracker.streamlit.app/`
  - Do not include GitHub.
- Healthcare M&A Case Decks
  - Use existing deck buttons with `data-deck="wuxi"` and `data-deck="sino"` only if duplicate buttons do not create confusing repeated modals. If duplicated buttons are used, existing JS will still bind them.
- Agilis Investment Memo
  - Use existing `data-deck="vcoc"` preview button.

3. Use labels like:

```text
CASE 01 · LIVE PRODUCT
CASE 02 · SELECTED TRANSACTION RESEARCH
CASE 03 · INVESTMENT MEMO
```

4. Verify internal anchor:

```bash
grep -n "id=\"selected-work\"\|CASE 01\|BioMarket Tracker" index.html
```

Expected: Selected Work section exists and has the BioMarket Tracker live link only.

5. Commit:

```bash
git add index.html && git commit -m "feat: add selected work section"
```

---

## Task 6: Reorder sections so Education comes after work

**Objective:** Make artifacts and experience precede education details.

**Files:**
- Modify: `index.html` body section order
- Modify: navigation links if needed

**Steps:**

1. Move the entire `<!-- Education -->` section from before Experience to after Projects/Research or after Experience, following the design spec order.

2. Recommended final visible order:

```text
Hero
Selected Work
About
Experience
Projects
Education
Skills
Contact
```

This keeps About early while still surfacing Selected Work immediately.

3. Update nav order to:

```html
<li><a href="#selected-work">Work</a></li>
<li><a href="#about">About</a></li>
<li><a href="#experience">Experience</a></li>
<li><a href="#projects">Projects</a></li>
<li><a href="#education">Education</a></li>
<li><a href="#contact">Contact</a></li>
```

4. Verify section order using browser or quick grep:

```bash
grep -n "<!-- Hero -->\|<!-- Selected Work -->\|<!-- About -->\|<!-- Experience -->\|<!-- Projects -->\|<!-- Education -->\|<!-- Skills -->\|<!-- Contact -->" index.html
```

Expected: line numbers increase in the intended order.

5. Commit:

```bash
git add index.html && git commit -m "feat: reorder personal site sections"
```

---

## Task 7: Standardize CGA/GPA and tighten content

**Objective:** Remove inconsistent academic numbers and avoid over-specific Tencent details.

**Files:**
- Modify: `index.html` About and Education text

**Steps:**

1. Replace all visible variants of `3.86`, `3.856 CGA`, and older GPA values with consistent wording:

```text
CGA: 3.856 / 4.3
```

2. If Hero no longer displays CGA, ensure only About/Education mention it.

3. Keep Tencent Ads high-level:

```html
<li>Conduct research on AI advertising, platform monetization, and competitive dynamics.</li>
```

4. Verify:

```bash
grep -n "3\.86\|3\.856\|3\.91\|Tencent Ads" index.html
```

Expected: no `3.86` or `3.91`; `3.856` appears only where intended.

5. Commit:

```bash
git add index.html && git commit -m "feat: standardize profile facts"
```

---

## Task 8: Update Contact with LinkedIn and live-site-only project link

**Objective:** Add LinkedIn and ensure BioMarket Tracker points only to the website.

**Files:**
- Modify: `index.html:1695-1758`
- Modify: `.contact-layout` grid CSS if four cards are used

**Steps:**

1. Add LinkedIn card using:

```html
<a href="https://www.linkedin.com/in/runze-zhu-8143b4380/" target="_blank" rel="noopener" class="contact-card reveal reveal-delay-4" aria-label="View Runze Zhu on LinkedIn">
```

2. Decide card count:

- Preferred: four cards — Email, LinkedIn, GitHub, BioMarket Tracker.
- If layout feels crowded, use four cards in a 2×2 desktop grid.

3. If using four cards, update CSS:

```css
.contact-layout {
  grid-template-columns: repeat(4, 1fr);
}

@media (max-width: 1080px) {
  .contact-layout { grid-template-columns: repeat(2, 1fr); }
}

@media (max-width: 860px) {
  .contact-layout { grid-template-columns: 1fr; }
}
```

4. Ensure BioMarket Tracker card links to live site only.

5. Verify:

```bash
grep -n "linkedin.com/in/runze-zhu-8143b4380\|runze-bio-market-tracker.streamlit.app\|github.com/LeoZhu6" index.html
```

Expected: LinkedIn exists; BioMarket Tracker live link exists; no BioMarket Tracker GitHub link was added.

6. Commit:

```bash
git add index.html && git commit -m "feat: update contact links"
```

---

## Task 9: Add image dimensions and performance polish

**Objective:** Reduce layout shift and prepare for image optimization.

**Files:**
- Modify: `index.html` image tags

**Steps:**

1. Add dimensions to `photo.jpg`:

```html
<img src="photo.jpg" alt="Runze Zhu" width="1050" height="1350">
```

2. Add dimensions to deck cover images:

```html
width="1280" height="720"
```

3. Keep deck images `loading="lazy"`.

4. Do not convert image formats in this pass unless explicitly requested.

5. Verify:

```bash
grep -n "width=\"1050\"\|width=\"1280\"\|loading=\"lazy\"" index.html
```

Expected: photo and deck covers include dimensions.

6. Commit:

```bash
git add index.html && git commit -m "perf: add image dimensions"
```

---

## Task 10: Full local verification

**Objective:** Prove the updated site works before reporting completion.

**Files:**
- No source changes unless issues are found.

**Steps:**

1. Run server:

```bash
python -m http.server 8765 --bind 127.0.0.1
```

2. Open:

```text
http://127.0.0.1:8765/index.html
```

3. Verify manually with browser tools:

- Hero headline and CTA are visible.
- Selected Work appears after Hero.
- Deck modals open and navigate.
- BioMarket Tracker links to the live site.
- LinkedIn opens the supplied URL.
- Contact cards fit desktop and mobile widths.
- No console errors.

4. Optional CLI checks:

```bash
grep -n "github.com/LeoZhu6/biotech-market-tracker" index.html || true
git status --short
```

Expected:

- No accidental BioMarket Tracker GitHub link.
- Git working tree clean after final commit.

5. Final commit only if verification fixes were needed:

```bash
git add index.html && git commit -m "fix: polish personal site verification issues"
```
