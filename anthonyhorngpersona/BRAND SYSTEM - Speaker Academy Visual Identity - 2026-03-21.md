---
created: 2026-03-21
updated: 2026-04-12
status: permanent
tags:
  - brand
  - visual-identity
  - colors
  - typography
  - speakeracademy
  - brand/speakeracademy
  - brand/prendslaparole
---

# BRAND SYSTEM — Speaker Academy Visual Identity
## Locked system as of March 21, 2026

> **This is the master document for Speaker Academy visual identity.** All other files referencing colors, fonts, or visual decisions defer to this file. If there is a conflict, this file wins.

---

## How This Was Built

Not derived from color psychology theory. Not invented from philosophy.

Built through a preference-driven process: options were generated, tested across real use cases, pressure tested across seven scenarios, and locked based on what held. The meaning layer was identified after the system was confirmed — not before.

---

## Colors — Four Values

| Role              | Name      | Hex       |
| ----------------- | --------- | --------- |
| Dominant surface  | White     | `#FFFFFF` |
| Secondary surface | Warm gray | `#F2F0EB` |
| Signal + accent   | Yellow    | `#F5D800` |
| Type + CTAs       | Black     | `#111111` |

### Usage Rules

**White** — primary background for all pages, posts, and content. Default surface.

**Warm gray** — secondary background only. Use for body copy slides, breathing room in long-form content, and alternating section backgrounds. Never use as the primary surface.

**Yellow** — accent only. One element per layout maximum. Works as a small, high-signal element. Breaks the moment it fills a large area with body text on top.

**Black** — all type, CTAs, and structural elements.

**Use yellow for:**
- Labels and badges
- Left-border quote accents
- Step number markers
- CTA button text on black backgrounds
- Small highlight blocks
- Thin rules and dividers in the logo and layout

**Never use yellow for:**
- Large background fills with body text
- Body text color
- More than 20% of any layout
- Decorative fills
- Both button and label on the same block simultaneously

### Why Four and Not Five

Color tools generate five because that is their model. You are not solving an aesthetic problem — you are solving a brand consistency problem. Every color added is another decision someone makes every time they create something. Four values means near-zero ambiguity.

A fifth value gets added only if a specific functional problem arises — a secondary state color for course interface (progress, completion, error). Not before.

### Meaning Layer

The connection that emerged and holds: yellow as the signal for attention — which maps directly to the core philosophy "attention is earned, not expected." Not invented retroactively as justification. Identified as a genuine alignment after the system was confirmed.

### Print Note

`#F5D800` can render pale on low-quality printers. In print-critical documents (PDFs, handouts), use a 2pt yellow rule or border instead of yellow fill blocks.

---

## Typography — Three Fonts, Two Contexts

### Logo — Bebas Neue
- Used exclusively for the wordmark
- All caps, condensed, heavy
- Not used anywhere else in the brand system
- Do not use Bebas Neue for headings, body, or UI

### Website and Marketing (everything you control)

| Role     | Font              | Weight                     |
| -------- | ----------------- | -------------------------- |
| Headings | Plus Jakarta Sans | 800                        |
| Body     | Inter             | 400 regular / 700 emphasis |

Both fonts are free on Google Fonts. Both are native in Canva. No custom installs required.

**Where these fonts apply:** Website pages, landing pages, sales pages, social content, PDFs, Canva templates, email headers.

**Where they do not apply:** Inside Kajabi course lesson content — see Kajabi note below.

### Why Plus Jakarta Sans (website + marketing headings)

Strong authority at heavy weight without the cold geometric temperature of Syne. Rounded terminals bring the visual register closer to human without sacrificing presence. The decision came from a direct ICP test: Segment 1 needs to feel recognized in the first three seconds, not evaluated. Syne read as a tech product. Plus Jakarta Sans reads as a person who knows what they are doing. The swap was made April 12, 2026 — see decision log at bottom.

### Why Inter (body)

The most legible screen body font available. Disappears into readability. Lets Plus Jakarta Sans do the work at headline size without fighting for attention.

---

## Kajabi Font Constraint

Kajabi controls the fonts available inside the course builder. Custom fonts (Plus Jakarta Sans, Inter) can be applied to:
- Website pages via theme editor CSS
- Landing pages and sales pages

Inside course lesson content, Kajabi uses its built-in font stack. This is a platform limitation — not a brand failure. The visual system holds through colors, logo, and layout consistency everywhere else.

**Practical rule:** Apply the full brand font system everywhere you control. Accept Kajabi's default fonts inside lesson content. The brand carries through color and logo consistency regardless.

---

## Logo — Locked March 21, 2026

### Structure
- Wordmark only — no icon
- Two lines stacked: SPEAKER over ACADEMY
- Both words flush left, same left edge X position
- Both words matching width edge to edge — SPEAKER sized larger to match ACADEMY width
- Yellow rule (`#F5D800`, 3px height) between the wordmark and the tagline — same width as ACADEMY, flush left
- Tagline underneath the yellow rule: YOU ARE THE MESSAGE (status: in use, final decision on permanent tagline pending)

### What the yellow rule does
Introduces the brand color once, precisely, without competing with the wordmark. Anchors the tagline visually. Signals the system without decorating it.

### Font
- Font: Bebas Neue (not Plus Jakarta Sans — Plus Jakarta Sans does not carry the required visual weight at logo scale)
- All caps — condensed, heavy, compressed
- Letter spacing: negative, tightened (-5 to -10 in Canva)
- Line spacing between the two words: 0.8 or tighter, boxes manually positioned in Canva

### Tagline font
- Inter Regular, all caps
- Letter spacing: wide (+5 to +10)
- Size: roughly 20-25% of the main wordmark size
- Color: `#111111`

### What it communicates
Power. Credibility. Permanence. The compressed block reads as an institution — something built to last, not launched to trend. The yellow rule ties it to the brand system without softening the weight.

### Canva notes
- Built as two separate text boxes (Canva limitation — cannot control inter-line spacing as one unit)
- Yellow rule added as a rectangle element: height 3px, color `#F5D800`, width matching ACADEMY text box
- Align all elements to the exact same X position using the Position panel
- Canvas size: 500x500px, background `#FFFFFF`
- Export: PNG, transparent background ON, 2x size

---

## System Behavior — Dark Variant

The system has two surfaces, not two separate systems.

**Light (default):** White surface, warm gray as secondary, yellow accent, black type.

**Dark (Reels, Stories, high-contrast moments):** Black surface, white type, yellow as the primary CTA and highlight element.

No new colors are introduced in the dark variant. The same four values invert.

---

## Pressure Test Results — March 21, 2026

| Test | Result | Notes |
|---|---|---|
| Small text legibility on yellow | PASS | Readable at heavy weight + dark brown text only. Never use behind body-size regular weight. |
| Yellow on dark background | PASS | Strongest combination in the system. High contrast, zero ambiguity. |
| Long-form content, no accent overuse | PASS | Yellow used once as label, once as quote border. Body copy pure black on white. |
| Yellow as full section background | FAIL | Illegible and harsh with body text. Documented rule: yellow must stay small. |
| Bilingual EN + FR side by side | PASS | Same system works across Speaker Academy and Académie Prends la parole. |
| Mobile-width social post at 260px | PASS | Dark header with yellow text, white body, yellow tag. Nothing breaks. |
| Print and PDF context | WATCH | Yellow prints well on standard printers. Low-quality printers may render pale. Use 2pt yellow rule instead of fills in print-critical docs. |

---

## Canva Brand Hub — Setup Values

- Primary background: `#FFFFFF`
- Secondary background: `#F2F0EB`
- Accent: `#F5D800`
- Type and CTAs: `#111111`
- Logo font: Bebas Neue
- Heading font: Plus Jakarta Sans 800
- Body font: Inter 400

---

## What the Viewer Sees

A yellow dot on a white page. High contrast, clean, modern. The black text confirms it is serious. The white space says it is not shouting. Warm gray enters when the content needs breathing room — never as a feature, always as a surface.

---

## Brand Separation Note

This system is for **Speaker Academy** (English course and coaching).

**Académie Prends la parole** shares the same visual system — same colors, same fonts, same rules. Distinguished by name and language only.

---

## Open Questions

- Final decision on whether Speaker Academy and Académie Prends la parole share one Canva Brand Kit or two identical ones
- "YOU ARE THE MESSAGE" — confirm as permanent tagline or replace

![[2.png]]
![[1.png]]

---

## Decision Log

| Date | Decision | Reason |
|---|---|---|
| April 12, 2026 | Heading font changed from Syne 800 to Plus Jakarta Sans 800 | Syne read as tech product — cool, geometric, impactful but not human. ICP test: Segment 1 needs to feel recognized in 3 seconds, not evaluated. Target temperature: Seth Godin — warm authority, ideas-first. Plus Jakarta Sans carries the same weight with rounded terminals that drop the emotional temperature to match. Wordmark (Bebas Neue) and body (Inter) unchanged. |
| April 12, 2026 | Warm gray `#F2F0EB` added as fourth color value | Previously missing from this file. Sourced from Brand Colors file (locked April 11, 2026). Colors section heading updated from "Three Values Only" to "Four Values." Canva Brand Hub and Dark Variant sections updated accordingly. |
