---
version: alpha
name: Apple Design System
description: Apple's light E-commerce design system — gallery-white canvas with enormous weight-700 headlines, zero-shadow elevation, and a single #0071e3 CTA color.
colors:
  ink: "#1d1d1f"
  graphite: "#707070"
  slate: "#474747"
  ash: "#333333"
  fog: "#f5f5f7"
  snow: "#ffffff"
  obsidian: "#000000"
  silver-mist: "#e8e8ed"
  azure: "#0071e3"
  cobalt-link: "#0066cc"
  citrus-finish: "#dddc8c"
  blush-finish: "#e8d0d0"
  indigo-finish: "#596680"
  caution: "#b64400"
  primary: "#1d1d1f"

typography:
  display:
    fontFamily: "SF Pro Display, Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, sans-serif"
    fontSize: 96px
    fontWeight: 700
    lineHeight: 1.04
    letterSpacing: "-0.022em"
  heading-lg:
    fontFamily: "SF Pro Display, Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, sans-serif"
    fontSize: 56px
    fontWeight: 700
    lineHeight: 1.07
    letterSpacing: "-0.016em"
  heading:
    fontFamily: "SF Pro Display, Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, sans-serif"
    fontSize: 40px
    fontWeight: 700
    lineHeight: 1.17
    letterSpacing: "-0.015em"
  heading-sm:
    fontFamily: "SF Pro Display, Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, sans-serif"
    fontSize: 24px
    fontWeight: 600
    lineHeight: 1.29
    letterSpacing: "-0.015em"
  subheading:
    fontFamily: "SF Pro Text, Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, sans-serif"
    fontSize: 20px
    fontWeight: 300
    lineHeight: 1.4
    letterSpacing: "-0.010em"
  body:
    fontFamily: "SF Pro Text, Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, sans-serif"
    fontSize: 17px
    fontWeight: 400
    lineHeight: 1.47
    letterSpacing: "-0.006em"
  body-sm:
    fontFamily: "SF Pro Text, Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, sans-serif"
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.43
    letterSpacing: "-0.003em"
  caption:
    fontFamily: "SF Pro Text, Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, sans-serif"
    fontSize: 12px
    fontWeight: 400
    lineHeight: 1.33
    letterSpacing: "-0.022em"

rounded:
  cards: 28px
  buttons: 999px
  navitems: 980px
  pillbuttons: 999px
  featurelinks: 28px
  smallbuttons: 10px
  roundedbuttons: 36px

spacing:
  "4": 4px
  "8": 8px
  "12": 12px
  "16": 16px
  "20": 20px
  "24": 24px
  "28": 28px
  "32": 32px
  "40": 40px
  "44": 44px
  "48": 48px
  "52": 52px
  "76": 76px
  "80": 80px
  "120": 120px
  "144": 144px

components:
  button-primary:
    backgroundColor: "{colors.azure}"
    textColor: "#ffffff"
    rounded: "{rounded.buttons}"
    padding: 8px 16px
    typography: "{typography.body}"
  button-dark-pill:
    backgroundColor: "{colors.obsidian}"
    textColor: "#ffffff"
    rounded: "{rounded.buttons}"
    padding: 8px 16px
  button-ghost:
    backgroundColor: transparent
    textColor: "{colors.ink}"
    rounded: 0px
  button-rounded-ghost:
    backgroundColor: transparent
    textColor: "{colors.ink}"
    rounded: "{rounded.featurelinks}"
  button-frosted-pill:
    backgroundColor: "rgba(210, 210, 215, 0.64)"
    textColor: "rgba(0, 0, 0, 0.56)"
    rounded: "{rounded.roundedbuttons}"
  card-white:
    backgroundColor: "{colors.snow}"
    rounded: "{rounded.cards}"
    padding: "{spacing.28}"
  card-fog:
    backgroundColor: "{colors.fog}"
    rounded: "{rounded.cards}"
    padding: "{spacing.28}"
  card-dark:
    backgroundColor: "{colors.obsidian}"
    rounded: "{rounded.cards}"
    padding: "{spacing.28}"
    textColor: "#ffffff"
  nav-global:
    backgroundColor: "{colors.fog}"
    height: 44px
  nav-product-sub:
    backgroundColor: "{colors.snow}"
    height: 52px
  swatch-chip:
    backgroundColor: "{colors.citrus-finish}"
    rounded: "{rounded.buttons}"
    size: 28px
---

## Overview

Apple's MacBook Neo product page radiates cool luminosity — a gallery-white
canvas where enormous weight-700 headlines at 80-96px dominate above
feather-light body copy, creating a tension between mass and air. The page
background stays #f5f5f7, one step off pure white, giving cards and content
wells a surface-lift effect without any shadows.

Negative letter-spacing tightens progressively with size — display headlines
track at -0.022em while body text breathes at -0.003em, a signature move that
makes large type feel chiseled rather than loose. The single interactive accent
(#0071e3 CTA blue) appears only on the Buy pill button and nav links, rationed
so every appearance reads as an instruction to act.

## Colors

- **Ink (#1d1d1f):** Primary text, headings, nav labels, icon fills — near-black with just enough warmth to avoid harshness on white.
- **Graphite (#707070):** Secondary body copy, captions, footnotes, muted nav items.
- **Slate (#474747):** Tertiary body text, supporting link text, secondary nav.
- **Ash (#333333):** Icon strokes, mid-weight body text, button labels in ghost state.
- **Fog (#f5f5f7):** Page canvas background, section divider bands, badge fills.
- **Snow (#ffffff):** Card surfaces, nav background, elevated container fills.
- **Obsidian (#000000):** Dark card variant, hero icon fills, maximum-contrast black card.
- **Silver Mist (#e8e8ed):** Frosted pill button background, input backgrounds.
- **Azure (#0071e3):** Primary CTA button fill — the sole permission-to-act color on the entire page.
- **Cobalt Link (#0066cc):** Inline text links — slightly darker than Azure to distinguish interactive text from buttons.
- **Caution (#b64400):** Badge warning text, price asterisk callouts — deep amber-orange.

## Typography

SF Pro Display for all marketing headlines above 24px (weight 700 at 40-96px,
weight 600 at 24px). SF Pro Text for body copy, nav labels, captions, and
button text (weight 400 at 17px default, weight 300 at larger marketing
subheadings).

Negative tracking tightens proportionally as font size increases:
- Display 96px: -0.022em
- Heading-lg 56px: -0.016em
- Heading 40px: -0.015em
- Body 17px: -0.006em
- Body-sm 14px: -0.003em

## Layout

Page max-width 1200px centered on #f5f5f7 canvas. Section rhythm alternates
between white (#ffffff) and fog (#f5f5f7) bands with no explicit dividers —
the color shift alone creates section breaks.

Hero is full-viewport centered headline stack (product name at 24px, hero
headline at 80-96px, price subtext at 17px, single Buy pill). Sub-nav becomes
sticky at 52px after hero scroll.

Feature sections use 2-column split (text left at ~40%, image right at ~60%)
or full-bleed product gradient cards. Cards are 28px border-radius — Apple's
geometric signature. Card padding: 28px.

## Elevation & Depth

Zero box-shadows across all card instances. Elevation is expressed entirely
through background-color differential: #ffffff cards float above #f5f5f7
canvas by value contrast alone. This forces the eye to read depth through
color rather than cast shadow.

Surface levels:
- 0 Canvas: #f5f5f7
- 1 Card: #ffffff
- 2 Recessed: #f5f5f7 (within white cards)
- 3 Frosted Control: rgba(210,210,215,0.64) with backdrop blur
- 4 Dark Stage: #000000

## Shapes

- Cards: 28px border-radius (signature Apple value)
- Buttons: 999px border-radius (fully rounded pills)
- Nav items: 980px border-radius
- Small buttons: 10px
- Frosted controls: 36px

## Components

`button-primary` is the sole conversion CTA. Background #0071e3, text #ffffff,
border-radius 999px. The only #0071e3 element on the page — isolated blue
against all-neutral surroundings makes it impossible to miss.

`card-white` lifts off the #f5f5f7 canvas by 1 surface level. 28px radius,
zero shadow. Text inside uses Ink for titles, Graphite for body.

`nav-global` is a persistent top nav at 44px height. Background #f5f5f7,
nav links at 12px SF Pro Text. Contains primary Buy button at far right.

`nav-product-sub` is a sticky page-section navigator at 52px height.
Background #ffffff, border-bottom 1px solid #e8e8ed. Active link has 3px
solid #1d1d1f underline.

## Do's and Don'ts

### Do
- Use 28px border-radius for all feature cards — this exact value is the page's geometric signature.
- Reserve #0071e3 exclusively for the primary CTA button.
- Apply negative letter-spacing scaled to font size.
- Use #f5f5f7 as page canvas and #ffffff as card surface. Never reverse.
- Set SF Pro Display weight 700 for all primary headlines at 56px and above.

### Don't
- Do not add box-shadow to any card or container. The entire elevation system is color-value-only.
- Do not use #0066cc (Cobalt Link) for button backgrounds.
- Do not use font weight 300 for headlines below 40px.
- Do not place two rounded-pill buttons side by side in the same visual zone.
- Do not center-align body paragraphs longer than 2 lines.
