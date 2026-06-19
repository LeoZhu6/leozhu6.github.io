# Personal Site Optimization Design

Date: 2026-06-19
Project: `D:\Project\personal-site`
Scope: design/specification only. This document does not change the live website implementation.

## 1. Goal

Optimize Runze Zhu's personal website from a clean resume-style page into a sharper personal brand site for a Finance + BioEngineering builder.

The site should communicate three things quickly:

1. Runze works at the intersection of finance, biotechnology, and AI analytics.
2. He has credible proof: HKUST, healthcare investment banking, Tencent AI ads research, VCOC Top 10, BioMarket Tracker.
3. He builds useful artifacts, not just lists credentials.

## 2. Target Positioning

Recommended positioning:

> Biotech finance, translated into investable insight.

Supporting description:

> HKUST BBA student exploring the intersection of capital markets, life sciences, and AI-driven research workflows — from healthcare M&A case decks to biotech equity analytics tools.

Tone:

- Professional but not corporate-generic.
- Research-dossier style rather than ordinary portfolio template.
- Trustworthy enough for finance recruiters, distinctive enough for builder/project audiences.

## 3. External Design References and Lessons

### Brittany Chiang

Takeaway: strong one-line professional identity and clear section hierarchy. Do not copy the dark developer portfolio style, but use the idea of immediate positioning.

### Lee Robinson

Takeaway: minimal site structure can work when writing, projects, and career proof are easy to scan. Use concise labels and direct links.

### Josh W Comeau

Takeaway: personality matters. A personal site should not feel like a static resume PDF converted to HTML.

### Maggie Appleton

Takeaway: visual essays and artifact-led storytelling build credibility. For this site, deck previews and product screenshots should become evidence, not decoration.

### Rauno Freiberg / Emil Kowalski

Takeaway: refined interaction design and small motion details can make a simple page feel premium. Keep motion subtle and purposeful.

### GitHub Portfolio Templates

Takeaway: many templates are useful for structure but too generic visually. Avoid a standard developer-portfolio aesthetic. Keep the current editorial direction and make it more specific to biotech finance.

## 4. Current Site Assessment

Current stack and structure:

- Static single-file website: `index.html`
- Assets:
  - `photo.jpg`
  - `assets/decks/*.jpg`
- Current visual system:
  - Warm ivory background
  - Dark brown/black text
  - Orange accent
  - Playfair Display headings
  - Inter body text
  - Scroll reveal animations
  - Counter animation
  - Custom cursor
  - Deck preview modal

Strengths:

- Clean, professional, and already visually coherent.
- Deck preview modal is a strong differentiator because it shows real artifacts.
- The warm editorial style is more distinctive than a standard resume website.
- No console errors in local browser testing.

Problems to address:

1. The site reads too much like a chronological resume; proof artifacts appear too late.
2. Education appears before the strongest evidence of work and projects.
3. Hero proof points include TOEFL, which is less differentiated than BioMarket Tracker, healthcare IB, or VCOC.
4. GPA appears inconsistently across the site and must be standardized before editing.
5. BioMarket Tracker lacks a visual screenshot, so the most important project is under-demonstrated.
6. Orange accent is polished but slightly generic Anthropic-like; a biotech finance palette would be more ownable.
7. Mobile navigation hides section links completely, reducing browsability.
8. Accessibility can be improved with focus states and reduced-motion handling.

## 5. Information Architecture

### Current order

1. Hero
2. About
3. Education
4. Experience
5. Projects
6. Skills
7. Contact

### Proposed order

1. Hero
2. Selected Work
3. Experience
4. Projects / Research Notes
5. Education
6. Skills
7. Contact

Rationale:

- Recruiters and collaborators should see artifacts and outcomes before education details.
- The strongest personal brand is not “student with experience”; it is “builder/researcher connecting biotech, finance, and AI.”
- Education remains important, but it supports the story rather than leading it.

## 6. Hero Design

### Recommended headline

> Biotech finance, translated into investable insight.

### Recommended subheadline

> I study Finance & BioEngineering at HKUST and build AI-driven research workflows for biotech markets, healthcare investing, and platform strategy.

### Primary CTA

`View selected work`

Target: new Selected Work section.

### Secondary CTA

`Launch BioMarket Tracker`

Target: `https://runze-bio-market-tracker.streamlit.app/`

### Proof strip

Replace the current GPA / Dean's List / TOEFL grouping with proof points that better support the site positioning:

- `HKUST BBA` — Finance + BioEngineering
- `Healthcare IB` — Haoyue Capital
- `Top 10 / 90` — VCOC Investment Challenge
- `Live Product` — BioMarket Tracker

If GPA remains in hero, use one standardized number across all sections.

## 7. Selected Work Section

Add a high-priority section immediately after the Hero.

Section title:

> Selected work across markets, science, and AI.

Structure: three evidence-led cards.

### Card 1: BioMarket Tracker

Purpose: position Runze as a builder.

Content:

- Title: `BioMarket Tracker`
- Label: `Live product · biotech equity analytics`
- Description: AI-driven biotech equity analysis platform with market data, Monte Carlo simulation, risk-adjusted valuation, and AI-generated research reports.
- Proof points:
  - Monte Carlo simulation
  - rNPV / risk-adjusted valuation
  - Streamlit + Python + Plotly
  - DeepSeek research workflow
- Links:
  - Launch App
  - View GitHub, if public and appropriate
- Visual:
  - Add a product screenshot or browser capture.

### Card 2: Healthcare M&A Case Decks

Purpose: show finance/investment banking artifact quality.

Content:

- Title: `Healthcare M&A Case Decks`
- Label: `Haoyue Capital · selected transaction research`
- Description: Case decks covering transaction rationale, valuation logic, buyer fit, and deal structure for healthcare M&A transactions.
- Artifacts:
  - WuXi XDC / TOT BIOPHARM
  - Sino Biopharmaceutical / HYGieia
- Interaction:
  - Keep existing modal deck preview.
  - Make the card feel like a case file rather than a thumbnail gallery.

### Card 3: VCOC Investment Memo

Purpose: show venture/investment judgement.

Content:

- Title: `Agilis Investment Memo`
- Label: `VCOC 2026 · Top 10 / 90 teams`
- Description: Product due diligence and investment thesis work connecting product logic, market sizing, valuation, and pitch development.
- Artifact:
  - Existing deck preview images.

## 8. Experience Section

Keep the clean two-column timeline structure, but make each experience more outcome-oriented.

Recommended format for each experience:

- Organization
- Role
- Date / location
- Focus area
- Outputs / artifacts
- Tags

### Tencent Ads

Current content is too short. Improve with high-level, non-confidential language:

- AI advertising research
- Platform monetization
- Competitive dynamics
- Research outputs or strategy memo format, if accurate and shareable

Do not invent confidential achievements or metrics.

### Haoyue Capital

Keep the current transaction references and attach selected deal decks as artifacts. Tighten wording around:

- transaction rationale
- valuation logic
- deal structure
- healthcare M&A context

### VCOC

Emphasize:

- Top 10 / 90 teams
- product due diligence
- investment thesis
- pitch development
- valuation support

### MSSSUG / HKUST Admissions

Keep concise. These support leadership and campus involvement but should not dominate the page.

## 9. Projects / Research Section

Projects should separate builder projects from competitions and notes.

### Featured project

BioMarket Tracker should be the dominant project card with visual evidence.

Needed additions:

- Screenshot
- Live demo link
- GitHub link if public
- Short feature bullets
- Technology tags

### Secondary work

- VCOC Investment Challenge
- HKUST Course Wiki
- Future: Tencent AI advertising research notes, if publishable
- Future: biotech market research notes or mini-essays

## 10. Education Section

Move Education after the work sections.

Keep it concise:

- HKUST BBA · Finance & BioEngineering
- CGA/GPA, standardized
- Dean's List
- relevant coursework
- Hanyang Winter School

Before implementation, confirm the correct GPA value and use it everywhere.

## 11. Skills Section

Current skills section is clear but can be more strategic.

Recommended grouping:

1. Finance & Investing
   - M&A analysis
   - DCF / rNPV
   - valuation
   - due diligence
   - pitch deck design

2. Data & AI
   - Python
   - Pandas
   - NumPy
   - Plotly
   - Streamlit
   - DeepSeek API
   - Monte Carlo simulation

3. Life Sciences & Research
   - biotech market research
   - pipeline analysis
   - scientific literature reading
   - Obsidian / LaTeX

This grouping better matches the target positioning than the current broad skill buckets.

## 12. Contact Section

Keep the three-card layout.

Add or verify:

- Email
- GitHub
- BioMarket Tracker
- Optional: LinkedIn if available

Recommended contact copy:

> Open to internships and projects across healthcare investment banking, biotech finance, AI research workflows, and product strategy.

## 13. Visual System

### Keep

- Warm editorial base
- Large serif headings
- Restrained body typography
- Premium spacing
- Deck modal interaction
- Smooth reveal animation

### Adjust

Move from generic warm-orange accent to a biotech finance palette.

Recommended tokens:

```css
--bg: #FAF8F2;
--bg-warm: #F1ECE2;
--bg-mid: #E8E0D3;
--ink: #191714;
--ink-60: rgba(25,23,20,0.62);
--accent: #4A7C59;
--accent-warm: #B66A3C;
--accent-dim: rgba(74,124,89,0.12);
--bg-dark: #25251F;
```

Rationale:

- Sage green connects to biotech/life sciences.
- Muted copper keeps the finance/editorial warmth.
- Dark olive/espresso grounds the page.

### Add research dossier language

Use visual motifs like:

- `CASE 01`
- `LIVE PRODUCT`
- `SELECTED TRANSACTION RESEARCH`
- `INVESTMENT MEMO`
- thin horizontal rules
- metadata rows
- compact labels

This makes the site feel like a curated body of work instead of a template portfolio.

## 14. Interaction and Motion

Keep existing interactions but refine them.

Required changes:

- Preserve scroll reveal.
- Preserve deck modal.
- Make card hover states subtle and consistent.
- Add visible keyboard focus states for links, buttons, and deck controls.
- Add `prefers-reduced-motion` handling:

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation: none !important;
    transition: none !important;
    scroll-behavior: auto !important;
  }
}
```

Avoid adding heavy 3D effects or generic animated gradients. They would weaken the professional finance/research tone.

## 15. Responsive Design

Current mobile behavior hides nav links. Improve mobile browsing.

Recommended mobile design:

- Keep logo and contact button.
- Add a horizontal scroll section nav below the top bar, or a simple menu button.
- Stack hero proof points vertically or in a compact two-column grid.
- Selected Work cards become single-column.
- Deck modal controls should remain large enough for touch input.
- About image should remain visible but not dominate the screen.

## 16. SEO and Metadata

Add or update:

- `meta name="description"`
- Open Graph tags
- Twitter card tags
- canonical URL if deployed as `leozhu6.github.io`
- meaningful page title

Recommended description:

> Runze Zhu is an HKUST BBA student studying Finance and BioEngineering, building AI-driven biotech market analytics tools and working across healthcare investment banking, venture research, and platform strategy.

## 17. Performance

Observed asset sizes:

- `photo.jpg`: about 656 KB, 1050 × 1350
- deck images: about 89–203 KB each, 1280 × 720

Recommended changes:

- Convert `photo.jpg` to WebP or AVIF.
- Add explicit `width` and `height` attributes for images where possible.
- Keep deck images lazy-loaded.
- Consider preloading the hero-critical portrait only if it remains above the fold.

## 18. Implementation Plan After Approval

Phase 1: Content and structure

1. Confirm standardized GPA.
2. Rewrite Hero headline/subheadline/proof strip.
3. Add Selected Work section after Hero.
4. Move Education below work sections.
5. Add BioMarket Tracker screenshot and link structure.

Phase 2: Visual refinement

1. Update color tokens.
2. Introduce research dossier labels and card styles.
3. Refine Selected Work cards.
4. Align deck cards with the new visual language.

Phase 3: Quality and accessibility

1. Add metadata and Open Graph tags.
2. Add focus states.
3. Add reduced-motion CSS.
4. Optimize images.
5. Improve mobile navigation.

Phase 4: Verification

1. Run local static server.
2. Test desktop viewport.
3. Test mobile viewport.
4. Click all internal nav links.
5. Click all external links.
6. Open and navigate deck modal.
7. Check browser console for JS errors.
8. Run Lighthouse or browser performance check if available.

## 19. Confirmed Implementation Decisions

Confirmed by user on 2026-06-19:

1. GPA/CGA source: use the attached resume/transcript as the factual source. Current HKUST CGA shown there is `3.856 / 4.3`. Avoid mixing `3.86`, `3.856`, and older values across sections.
2. BioMarket Tracker links: use the live website link only. Do not add a GitHub link for this project.
3. Contact: add LinkedIn using `https://www.linkedin.com/in/runze-zhu-8143b4380/`.
4. Tencent Ads: keep content high-level only. Do not write specific/confidential project details.
5. Visual direction: proceed with the recommended biotech sage green + muted copper palette.

## 20. Success Criteria

The redesign succeeds if:

- The first screen clearly communicates Runze's biotech finance builder identity.
- The strongest artifacts are visible within the first two scrolls.
- BioMarket Tracker has visual proof, not just text.
- The site feels more like a curated research/investment dossier than a resume template.
- All content remains factual and non-confidential.
- Mobile layout remains readable and navigable.
- Browser console remains free of errors.
